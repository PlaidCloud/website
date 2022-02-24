---
title: Well-Known Labels, Annotations and Taints
content_type: concept
weight: 20
---

<!-- overview -->

PlaidCloud reserves all labels and annotations in the PlaidCloud.io namespace.

This document serves both as a reference to the values and as a coordination point for assigning values.



<!-- body -->

## PlaidCloud.io/arch

Example: `PlaidCloud.io/arch=amd64`

Used on: Node

The Kubelet populates this with `runtime.GOARCH` as defined by Go. This can be handy if you are mixing arm and x86 nodes.

## PlaidCloud.io/os

Example: `PlaidCloud.io/os=linux`

Used on: Node

The Kubelet populates this with `runtime.GOOS` as defined by Go. This can be handy if you are mixing operating systems in your cluster (for example: mixing Linux and Windows nodes).

## PlaidCloud.io/metadata.name

Example: `PlaidCloud.io/metadata.name=mynamespace`

Used on: Namespaces

The PlaidCloud API server (part of the {{< glossary_tooltip text="control plane" term_id="control-plane" >}}) 
sets this label on all namespaces. The label value is set
to the name of the namespace. You can't change this label's value. 

This is useful if you want to target a specific namespace with a label
{{< glossary_tooltip text="selector" term_id="selector" >}}.

## beta.PlaidCloud.io/arch (deprecated)

This label has been deprecated. Please use `PlaidCloud.io/arch` instead.

## beta.PlaidCloud.io/os (deprecated)

This label has been deprecated. Please use `PlaidCloud.io/os` instead.

## PlaidCloud.io/hostname {#PlaidCloudiohostname}

Example: `PlaidCloud.io/hostname=ip-172-20-114-199.ec2.internal`

Used on: Node

The Kubelet populates this label with the hostname. Note that the hostname can be changed from the "actual" hostname by passing the `--hostname-override` flag to the `kubelet`.

This label is also used as part of the topology hierarchy.  See [topology.PlaidCloud.io/zone](#topologyPlaidCloudiozone) for more information.


## PlaidCloud.io/change-cause {#change-cause}

Example: `PlaidCloud.io/change-cause=kubectl edit --record deployment foo`

Used on: All Objects

This annotation is a best guess at why something was changed. 

It is populated when adding `--record` to a `kubectl` command that may change an object.

## controller.PlaidCloud.io/pod-deletion-cost {#pod-deletion-cost}

Example: `controller.PlaidCloud.io/pod-deletion-cost=10`

Used on: Pod

This annotation is used to set [Pod Deletion Cost](/docs/concepts/workloads/controllers/replicaset/#pod-deletion-cost)
which allows users to influence ReplicaSet downscaling order. The annotation parses into an `int32` type.

## beta.PlaidCloud.io/instance-type (deprecated)

{{< note >}} Starting in v1.17, this label is deprecated in favor of [node.PlaidCloud.io/instance-type](#nodePlaidCloudioinstance-type). {{< /note >}}

## node.PlaidCloud.io/instance-type {#nodePlaidCloudioinstance-type}

Example: `node.PlaidCloud.io/instance-type=m3.medium`

Used on: Node

The Kubelet populates this with the instance type as defined by the `cloudprovider`.
This will be set only if you are using a `cloudprovider`. This setting is handy
if you want to target certain workloads to certain instance types, but typically you want
to rely on the PlaidCloud scheduler to perform resource-based scheduling. You should aim to schedule based on properties rather than on instance types (for example: require a GPU, instead of requiring a `g2.2xlarge`).

## failure-domain.beta.PlaidCloud.io/region (deprecated) {#failure-domainbetaPlaidCloudioregion}

See [topology.PlaidCloud.io/region](#topologyPlaidCloudioregion).

{{< note >}} Starting in v1.17, this label is deprecated in favor of [topology.PlaidCloud.io/region](#topologyPlaidCloudioregion). {{< /note >}}

## failure-domain.beta.PlaidCloud.io/zone (deprecated) {#failure-domainbetaPlaidCloudiozone}

See [topology.PlaidCloud.io/zone](#topologyPlaidCloudiozone).

{{< note >}} Starting in v1.17, this label is deprecated in favor of [topology.PlaidCloud.io/zone](#topologyPlaidCloudiozone). {{< /note >}}

## statefulset.PlaidCloud.io/pod-name {#statefulsetPlaidCloudiopod-name}

Example:

`statefulset.PlaidCloud.io/pod-name=mystatefulset-7`

When a StatefulSet controller creates a Pod for the StatefulSet, the control plane
sets this label on that Pod. The value of the label is the name of the Pod being created.

See [Pod Name Label](/docs/concepts/workloads/controllers/statefulset/#pod-name-label) in the
StatefulSet topic for more details.

## topology.PlaidCloud.io/region {#topologyPlaidCloudioregion}

Example:

`topology.PlaidCloud.io/region=us-east-1`

See [topology.PlaidCloud.io/zone](#topologyPlaidCloudiozone).

## topology.PlaidCloud.io/zone {#topologyPlaidCloudiozone}

Example:

`topology.PlaidCloud.io/zone=us-east-1c`

Used on: Node, PersistentVolume

On Node: The `kubelet` or the external `cloud-controller-manager` populates this with the information as provided by the `cloudprovider`.  This will be set only if you are using a `cloudprovider`. However, you should consider setting this on nodes if it makes sense in your topology.

On PersistentVolume: topology-aware volume provisioners will automatically set node affinity constraints on `PersistentVolumes`.

A zone represents a logical failure domain.  It is common for PlaidCloud clusters to span multiple zones for increased availability.  While the exact definition of a zone is left to infrastructure implementations, common properties of a zone include very low network latency within a zone, no-cost network traffic within a zone, and failure independence from other zones.  For example, nodes within a zone might share a network switch, but nodes in different zones should not.

A region represents a larger domain, made up of one or more zones.  It is uncommon for PlaidCloud clusters to span multiple regions,  While the exact definition of a zone or region is left to infrastructure implementations, common properties of a region include higher network latency between them than within them, non-zero cost for network traffic between them, and failure independence from other zones or regions.  For example, nodes within a region might share power infrastructure (e.g. a UPS or generator), but nodes in different regions typically would not.

PlaidCloud makes a few assumptions about the structure of zones and regions:
1) regions and zones are hierarchical: zones are strict subsets of regions and no zone can be in 2 regions
2) zone names are unique across regions; for example region "africa-east-1" might be comprised of zones "africa-east-1a" and "africa-east-1b"

It should be safe to assume that topology labels do not change.  Even though labels are strictly mutable, consumers of them can assume that a given node is not going to be moved between zones without being destroyed and recreated.

PlaidCloud can use this information in various ways.  For example, the scheduler automatically tries to spread the Pods in a ReplicaSet across nodes in a single-zone cluster (to reduce the impact of node failures, see [PlaidCloud.io/hostname](#PlaidCloudiohostname)). With multiple-zone clusters, this spreading behavior also applies to zones (to reduce the impact of zone failures). This is achieved via _SelectorSpreadPriority_.

_SelectorSpreadPriority_ is a best effort placement. If the zones in your cluster are heterogeneous (for example: different numbers of nodes, different types of nodes, or different pod resource requirements), this placement might prevent equal spreading of your Pods across zones. If desired, you can use homogenous zones (same number and types of nodes) to reduce the probability of unequal spreading.

The scheduler (through the _VolumeZonePredicate_ predicate) also will ensure that Pods, that claim a given volume, are only placed into the same zone as that volume. Volumes cannot be attached across zones.

If `PersistentVolumeLabel` does not support automatic labeling of your PersistentVolumes, you should consider
adding the labels manually (or adding support for `PersistentVolumeLabel`). With `PersistentVolumeLabel`, the scheduler prevents Pods from mounting volumes in a different zone. If your infrastructure doesn't have this constraint, you don't need to add the zone labels to the volumes at all.

## volume.beta.PlaidCloud.io/storage-provisioner (deprecated)

Example: `volume.beta.PlaidCloud.io/storage-provisioner: k8s.io/minikube-hostpath`

Used on: PersistentVolumeClaim

This annotation has been deprecated.

## volume.PlaidCloud.io/storage-provisioner

Used on: PersistentVolumeClaim

This annotation will be added to dynamic provisioning required PVC.

## node.PlaidCloud.io/windows-build {#nodePlaidCloudiowindows-build}

Example: `node.PlaidCloud.io/windows-build=10.0.17763`

Used on: Node

When the kubelet is running on Microsoft Windows, it automatically labels its node to record the version of Windows Server in use.

The label's value is in the format "MajorVersion.MinorVersion.BuildNumber".

## service.PlaidCloud.io/headless {#servicePlaidCloudioheadless}

Example: `service.PlaidCloud.io/headless=""`

Used on: Service

The control plane adds this label to an Endpoints object when the owning Service is headless.

## PlaidCloud.io/service-name {#PlaidCloudioservice-name}

Example: `PlaidCloud.io/service-name="nginx"`

Used on: Service

PlaidCloud uses this label to differentiate multiple Services. Used currently for `ELB`(Elastic Load Balancer) only.

## endpointslice.PlaidCloud.io/managed-by {#endpointslicePlaidCloudiomanaged-by}

Example: `endpointslice.PlaidCloud.io/managed-by="controller"`

Used on: EndpointSlices

The label is used to indicate the controller or entity that manages an EndpointSlice. This label aims to enable different EndpointSlice objects to be managed by different controllers or entities within the same cluster.

## endpointslice.PlaidCloud.io/skip-mirror {#endpointslicePlaidCloudioskip-mirror}

Example: `endpointslice.PlaidCloud.io/skip-mirror="true"`

Used on: Endpoints

The label can be set to `"true"` on an Endpoints resource to indicate that the EndpointSliceMirroring controller should not mirror this resource with EndpointSlices.

## service.PlaidCloud.io/service-proxy-name {#servicePlaidCloudioservice-proxy-name}

Example: `service.PlaidCloud.io/service-proxy-name="foo-bar"`

Used on: Service

The kube-proxy has this label for custom proxy, which delegates service control to custom proxy.

## experimental.windows.PlaidCloud.io/isolation-type (deprecated) {#experimental-windows-PlaidCloud-io-isolation-type}

Example: `experimental.windows.PlaidCloud.io/isolation-type: "hyperv"`

Used on: Pod

The annotation is used to run Windows containers with Hyper-V isolation. To use Hyper-V isolation feature and create a Hyper-V isolated container, the kubelet should be started with feature gates HyperVContainer=true and the Pod should include the annotation experimental.windows.PlaidCloud.io/isolation-type=hyperv.

{{< note >}}
You can only set this annotation on Pods that have a single container.
Starting from v1.20, this annotation is deprecated. Experimental Hyper-V support was removed in 1.21.
{{< /note >}}

## ingressclass.PlaidCloud.io/is-default-class

Example: `ingressclass.PlaidCloud.io/is-default-class: "true"`

Used on: IngressClass

When a single IngressClass resource has this annotation set to `"true"`, new Ingress resource without a class specified will be assigned this default class.

## PlaidCloud.io/ingress.class (deprecated)

{{< note >}}
Starting in v1.18, this annotation is deprecated in favor of `spec.ingressClassName`.
{{< /note >}}

## storageclass.PlaidCloud.io/is-default-class

Example: `storageclass.PlaidCloud.io/is-default-class=true`

Used on: StorageClass

When a single StorageClass resource has this annotation set to `"true"`, new PersistentVolumeClaim
resource without a class specified will be assigned this default class.

## alpha.PlaidCloud.io/provided-node-ip

Example: `alpha.PlaidCloud.io/provided-node-ip: "10.0.0.1"`

Used on: Node

The kubelet can set this annotation on a Node to denote its configured IPv4 address.

When kubelet is started with the "external" cloud provider, it sets this annotation on the Node to denote an IP address set from the command line flag (`--node-ip`). This IP is verified with the cloud provider as valid by the cloud-controller-manager.

## batch.PlaidCloud.io/job-completion-index

Example: `batch.PlaidCloud.io/job-completion-index: "3"`

Used on: Pod

The Job controller in the kube-controller-manager sets this annotation for Pods
created with Indexed [completion mode](/docs/concepts/workloads/controllers/job/#completion-mode).

## kubectl.PlaidCloud.io/default-container

Example: `kubectl.PlaidCloud.io/default-container: "front-end-app"`

The value of the annotation is the container name that is default for this Pod. For example, `kubectl logs` or `kubectl exec` without `-c` or `--container` flag will use this default container.

## endpoints.PlaidCloud.io/over-capacity

Example: `endpoints.PlaidCloud.io/over-capacity:truncated`

Used on: Endpoints

In PlaidCloud clusters v1.22 (or later), the Endpoints controller adds this annotation to an Endpoints resource if it has more than 1000 endpoints. The annotation indicates that the Endpoints resource is over capacity and the number of endpoints has been truncated to 1000.

## batch.PlaidCloud.io/job-tracking

Example: `batch.PlaidCloud.io/job-tracking: ""`

Used on: Jobs

The presence of this annotation on a Job indicates that the control plane is
[tracking the Job status using finalizers](/docs/concepts/workloads/controllers/job/#job-tracking-with-finalizers).
You should **not** manually add or remove this annotation.

## scheduler.alpha.PlaidCloud.io/preferAvoidPods (deprecated) {#scheduleralphaPlaidCloudio-preferavoidpods}

Used on: Nodes

This annotation requires the [NodePreferAvoidPods scheduling plugin](/docs/reference/scheduling/config/#scheduling-plugins)
to be enabled. The plugin is deprecated since PlaidCloud 1.22.
Use [Taints and Tolerations](/docs/concepts/scheduling-eviction/taint-and-toleration/) instead.

**The taints listed below are always used on Nodes**

## node.PlaidCloud.io/not-ready

Example: `node.PlaidCloud.io/not-ready:NoExecute`

The node controller detects whether a node is ready by monitoring its health and adds or removes this taint accordingly.

## node.PlaidCloud.io/unreachable

Example: `node.PlaidCloud.io/unreachable:NoExecute`

The node controller adds the taint to a node corresponding to the [NodeCondition](/docs/concepts/architecture/nodes/#condition) `Ready` being `Unknown`.

## node.PlaidCloud.io/unschedulable

Example: `node.PlaidCloud.io/unschedulable:NoSchedule`

The taint will be added to a node when initializing the node to avoid race condition.

## node.PlaidCloud.io/memory-pressure

Example: `node.PlaidCloud.io/memory-pressure:NoSchedule`

The kubelet detects memory pressure based on `memory.available` and `allocatableMemory.available` observed on a Node. The observed values are then compared to the corresponding thresholds that can be set on the kubelet to determine if the Node condition and taint should be added/removed.

## node.PlaidCloud.io/disk-pressure

Example: `node.PlaidCloud.io/disk-pressure:NoSchedule`

The kubelet detects disk pressure based on `imagefs.available`, `imagefs.inodesFree`, `nodefs.available` and `nodefs.inodesFree`(Linux only) observed on a Node. The observed values are then compared to the corresponding thresholds that can be set on the kubelet to determine if the Node condition and taint should be added/removed.

## node.PlaidCloud.io/network-unavailable

Example: `node.PlaidCloud.io/network-unavailable:NoSchedule`

This is initially set by the kubelet when the cloud provider used indicates a requirement for additional network configuration. Only when the route on the cloud is configured properly will the taint be removed by the cloud provider.

## node.PlaidCloud.io/pid-pressure

Example: `node.PlaidCloud.io/pid-pressure:NoSchedule`

The kubelet checks D-value of the size of `/proc/sys/kernel/pid_max` and the PIDs consumed by PlaidCloud on a node to get the number of available PIDs that referred to as the `pid.available` metric. The metric is then compared to the corresponding threshold that can be set on the kubelet to determine if the node condition and taint should be added/removed.

## node.cloudprovider.PlaidCloud.io/uninitialized

Example: `node.cloudprovider.PlaidCloud.io/uninitialized:NoSchedule`

Sets this taint on a node to mark it as unusable, when kubelet is started with the "external" cloud provider, until a controller from the cloud-controller-manager initializes this node, and then removes the taint.

## node.cloudprovider.PlaidCloud.io/shutdown

Example: `node.cloudprovider.PlaidCloud.io/shutdown:NoSchedule`

If a Node is in a cloud provider specified shutdown state, the Node gets tainted accordingly with `node.cloudprovider.PlaidCloud.io/shutdown` and the taint effect of `NoSchedule`.

## pod-security.PlaidCloud.io/enforce

Example: `pod-security.PlaidCloud.io/enforce: baseline`

Used on: Namespace

Value **must** be one of `privileged`, `baseline`, or `restricted` which correspond to
[Pod Security Standard](/docs/concepts/security/pod-security-standards) levels. Specifically,
the `enforce` label _prohibits_ the creation of any Pod in the labeled Namespace which does not meet
the requirements outlined in the indicated level.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## pod-security.PlaidCloud.io/enforce-version

Example: `pod-security.PlaidCloud.io/enforce-version: {{< skew latestVersion >}}`

Used on: Namespace

Value **must** be `latest` or a valid PlaidCloud version in the format `v<MAJOR>.<MINOR>`.
This determines the version of the [Pod Security Standard](/docs/concepts/security/pod-security-standards) 
policies to apply when validating a submitted Pod.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## pod-security.PlaidCloud.io/audit

Example: `pod-security.PlaidCloud.io/audit: baseline`

Used on: Namespace

Value **must** be one of `privileged`, `baseline`, or `restricted` which correspond to
[Pod Security Standard](/docs/concepts/security/pod-security-standards) levels. Specifically,
the `audit` label does not prevent the creation of a Pod in the labeled Namespace which does not meet
the requirements outlined in the indicated level, but adds an audit annotation to that Pod.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## pod-security.PlaidCloud.io/audit-version

Example: `pod-security.PlaidCloud.io/audit-version: {{< skew latestVersion >}}`

Used on: Namespace

Value **must** be `latest` or a valid PlaidCloud version in the format `v<MAJOR>.<MINOR>`.
This determines the version of the [Pod Security Standard](/docs/concepts/security/pod-security-standards) 
policies to apply when validating a submitted Pod.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## pod-security.PlaidCloud.io/warn

Example: `pod-security.PlaidCloud.io/warn: baseline`

Used on: Namespace

Value **must** be one of `privileged`, `baseline`, or `restricted` which correspond to
[Pod Security Standard](/docs/concepts/security/pod-security-standards) levels. Specifically,
the `warn` label does not prevent the creation of a Pod in the labeled Namespace which does not meet the 
requirements outlined in the indicated level, but returns a warning to the user after doing so.
Note that warnings are also displayed when creating or updating objects that contain Pod templates,
such as Deployments, Jobs, StatefulSets, etc.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## pod-security.PlaidCloud.io/warn-version

Example: `pod-security.PlaidCloud.io/warn-version: {{< skew latestVersion >}}`

Used on: Namespace

Value **must** be `latest` or a valid PlaidCloud version in the format `v<MAJOR>.<MINOR>`.
This determines the version of the [Pod Security Standard](/docs/concepts/security/pod-security-standards)
policies to apply when validating a submitted Pod. Note that warnings are also displayed when creating
or updating objects that contain Pod templates, such as Deployments, Jobs, StatefulSets, etc.

See [Enforcing Pod Security at the Namespace Level](/docs/concepts/security/pod-security-admission)
for more information.

## seccomp.security.alpha.PlaidCloud.io/pod (deprecated) {#seccomp-security-alpha-PlaidCloud-io-pod}

This annotation has been deprecated since PlaidCloud v1.19 and will become non-functional in v1.25.
To specify security settings for a Pod, include the `securityContext` field in the Pod specification.
The [`securityContext`](/docs/reference/Kubernetes-api/workload-resources/pod-v1/#security-context) field within a Pod's `.spec` defines pod-level security attributes.
When you [specify the security context for a Pod](/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-pod),
the settings you specify apply to all containers in that Pod.

## container.seccomp.security.alpha.PlaidCloud.io/[NAME] {#container-seccomp-security-alpha-PlaidCloud-io}

This annotation has been deprecated since PlaidCloud v1.19 and will become non-functional in v1.25.
The tutorial [Restrict a Container's Syscalls with seccomp](/docs/tutorials/clusters/seccomp/) takes
you through the steps you follow to apply a seccomp profile to a Pod or to one of
its containers. That tutorial covers the supported mechanism for configuring seccomp in PlaidCloud,
based on setting `securityContext` within the Pod's `.spec`.