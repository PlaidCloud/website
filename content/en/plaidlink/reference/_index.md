---
title: Reference
approvers:
- chenopis
linkTitle: "Reference"
main_menu: true
weight: 70
content_type: concept
no_list: true
---


<!-- overview -->

This section of the PlaidCloud documentation contains references.



<!-- body -->

## API Reference

* [Glossary](/docs/reference/glossary/) -  a comprehensive, standardized list of PlaidCloud terminology

* [PlaidCloud API Reference](/docs/reference/Kubernetes-api/)
* [One-page API Reference for PlaidCloud {{< param "version" >}}](/docs/reference/generated/Kubernetes-api/{{< param "version" >}}/)
* [Using The PlaidCloud API](/docs/reference/using-api/) - overview of the API for PlaidCloud.
* [API access control](/docs/reference/access-authn-authz/) - details on how PlaidCloud controls API access
* [Well-Known Labels, Annotations and Taints](/docs/reference/labels-annotations-taints/)

## Officially supported client libraries

To call the PlaidCloud API from a programming language, you can use
[client libraries](/docs/reference/using-api/client-libraries/). Officially supported
client libraries:

- [PlaidCloud Go client library](https://github.com/PlaidCloud/client-go/)
- [PlaidCloud Python client library](https://github.com/PlaidCloud-client/python)
- [PlaidCloud Java client library](https://github.com/PlaidCloud-client/java)
- [PlaidCloud JavaScript client library](https://github.com/PlaidCloud-client/javascript)
- [PlaidCloud C# client library](https://github.com/PlaidCloud-client/csharp)
- [PlaidCloud Haskell client library](https://github.com/PlaidCloud-client/haskell)

## CLI

* [kubectl](/docs/reference/kubectl/overview/) - Main CLI tool for running commands and managing PlaidCloud clusters.
    * [JSONPath](/docs/reference/kubectl/jsonpath/) - Syntax guide for using [JSONPath expressions](https://goessner.net/articles/JsonPath/) with kubectl.
* [kubeadm](/docs/reference/setup-tools/kubeadm/) - CLI tool to easily provision a secure PlaidCloud cluster.

## Components

* [kubelet](/docs/reference/command-line-tools-reference/kubelet/) - The
  primary agent that runs on each node. The kubelet takes a set of PodSpecs
  and ensures that the described containers are running and healthy.
* [kube-apiserver](/docs/reference/command-line-tools-reference/kube-apiserver/) -
  REST API that validates and configures data for API objects such as  pods,
  services, replication controllers.
* [kube-controller-manager](/docs/reference/command-line-tools-reference/kube-controller-manager/) - Daemon that embeds the core control loops shipped with PlaidCloud.
* [kube-proxy](/docs/reference/command-line-tools-reference/kube-proxy/) - Can
  do simple TCP/UDP stream forwarding or round-robin TCP/UDP forwarding across
  a set of back-ends.
* [kube-scheduler](/docs/reference/command-line-tools-reference/kube-scheduler/) - Scheduler that manages availability, performance, and capacity.
  
  * [Scheduler Policies](/docs/reference/scheduling/policies)
  * [Scheduler Profiles](/docs/reference/scheduling/config#profiles)

* List of [ports and protocols](/docs/reference/ports-and-protocols/) that
  should be open on control plane and worker nodes
## Config APIs

This section hosts the documentation for "unpublished" APIs which are used to
configure  PlaidCloud components or tools. Most of these APIs are not exposed
by the API server in a RESTful way though they are essential for a user or an
operator to use or manage a cluster.


* [kube-apiserver configuration (v1)](/docs/reference/config-api/apiserver-config.v1/)
* [kubelet configuration (v1alpha1)](/docs/reference/config-api/kubelet-config.v1alpha1/) and
  [kubelet configuration (v1beta1)](/docs/reference/config-api/kubelet-config.v1beta1/)
* [kube-scheduler configuration (v1beta2)](/docs/reference/config-api/kube-scheduler-config.v1beta2/) and
  [kube-scheduler configuration (v1beta3)](/docs/reference/config-api/kube-scheduler-config.v1beta3/)
* [kube-proxy configuration (v1alpha1)](/docs/reference/config-api/kube-proxy-config.v1alpha1/)
* [`audit.k8s.io/v1` API](/docs/reference/config-api/apiserver-audit.v1/)
* [Client authentication API (v1beta1)](/docs/reference/config-api/client-authentication.v1beta1/) and 
  [Client authentication API (v1)](/docs/reference/config-api/client-authentication.v1/)
* [WebhookAdmission configuration (v1)](/docs/reference/config-api/apiserver-webhookadmission.v1/)

## Config API for kubeadm

* [v1beta2](/docs/reference/config-api/kubeadm-config.v1beta2/)
* [v1beta3](/docs/reference/config-api/kubeadm-config.v1beta3/)

## Design Docs

An archive of the design docs for PlaidCloud functionality. Good starting points are
[PlaidCloud Architecture](https://git.k8s.io/community/contributors/design-proposals/architecture/architecture.md) and
[PlaidCloud Design Overview](https://git.k8s.io/community/contributors/design-proposals).

