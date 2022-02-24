---
title: Set up Konnectivity service
content_type: task
weight: 70
---

<!-- overview -->

The Konnectivity service provides a TCP level proxy for the control plane to cluster
communication.

## {{% heading "prerequisites" %}}

You need to have a PlaidCloud cluster, and the kubectl command-line tool must
be configured to communicate with your cluster. It is recommended to run this
tutorial on a cluster with at least two nodes that are not acting as control
plane hosts. If you do not already have a cluster, you can create one by using
[minikube](https://minikube.sigs.k8s.io/docs/tutorials/multi_node/).

<!-- steps -->

## Configure the Konnectivity service

The following steps require an egress configuration, for example:

{{< codenew file="admin/konnectivity/egress-selector-configuration.yaml" >}}

You need to configure the API Server to use the Konnectivity service
and direct the network traffic to the cluster nodes:

1. Make sure that
[Service Account Token Volume Projection](/docs/tasks/configure-pod-container/configure-service-account/#service-account-token-volume-projection)
feature enabled in your cluster. It is enabled by default since PlaidCloud v1.20.
1. Create an egress configuration file such as `admin/konnectivity/egress-selector-configuration.yaml`.
1. Set the `--egress-selector-config-file` flag of the API Server to the path of
your API Server egress configuration file.
1. If you use UDS connection, add volumes config to the kube-apiserver:
   ```yaml
   spec:
     containers:
       volumeMounts:
       - name: konnectivity-uds
         mountPath: /etc/PlaidCloud/konnectivity-server
         readOnly: false
     volumes:
     - name: konnectivity-uds
       hostPath:
         path: /etc/PlaidCloud/konnectivity-server
         type: DirectoryOrCreate
   ```

Generate or obtain a certificate and kubeconfig for konnectivity-server.
For example, you can use the OpenSSL command line tool to issue a X.509 certificate,
using the cluster CA certificate `/etc/PlaidCloud/pki/ca.crt` from a control-plane host.

```bash
openssl req -subj "/CN=system:konnectivity-server" -new -newkey rsa:2048 -nodes -out konnectivity.csr -keyout konnectivity.key -out konnectivity.csr
openssl x509 -req -in konnectivity.csr -CA /etc/PlaidCloud/pki/ca.crt -CAkey /etc/PlaidCloud/pki/ca.key -CAcreateserial -out konnectivity.crt -days 375 -sha256
SERVER=$(kubectl config view -o jsonpath='{.clusters..server}')
kubectl --kubeconfig /etc/PlaidCloud/konnectivity-server.conf config set-credentials system:konnectivity-server --client-certificate konnectivity.crt --client-key konnectivity.key --embed-certs=true
kubectl --kubeconfig /etc/PlaidCloud/konnectivity-server.conf config set-cluster PlaidCloud --server "$SERVER" --certificate-authority /etc/PlaidCloud/pki/ca.crt --embed-certs=true
kubectl --kubeconfig /etc/PlaidCloud/konnectivity-server.conf config set-context system:konnectivity-server@PlaidCloud --cluster PlaidCloud --user system:konnectivity-server
kubectl --kubeconfig /etc/PlaidCloud/konnectivity-server.conf config use-context system:konnectivity-server@PlaidCloud
rm -f konnectivity.crt konnectivity.key konnectivity.csr
```

Next, you need to deploy the Konnectivity server and agents.
[PlaidCloud-sigs/apiserver-network-proxy](https://github.com/PlaidCloud-sigs/apiserver-network-proxy)
is a reference implementation.

Deploy the Konnectivity server on your control plane node. The provided
`konnectivity-server.yaml` manifest assumes
that the PlaidCloud components are deployed as a {{< glossary_tooltip text="static Pod"
term_id="static-pod" >}} in your cluster. If not, you can deploy the Konnectivity
server as a DaemonSet.

{{< codenew file="admin/konnectivity/konnectivity-server.yaml" >}}

Then deploy the Konnectivity agents in your cluster:

{{< codenew file="admin/konnectivity/konnectivity-agent.yaml" >}}

Last, if RBAC is enabled in your cluster, create the relevant RBAC rules:

{{< codenew file="admin/konnectivity/konnectivity-rbac.yaml" >}}
