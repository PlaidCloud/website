---
title: Understanding PlaidCloud Objects
content_type: concept
weight: 10
card: 
  name: concepts
  weight: 40
---

<!-- overview -->
This page explains how PlaidCloud objects are represented in the PlaidCloud API, and how you can express them in `.yaml` format.


<!-- body -->
## Understanding PlaidCloud objects {#PlaidCloud-objects}

*PlaidCloud objects* are persistent entities in the PlaidCloud system. PlaidCloud uses these entities to represent the state of your cluster. Specifically, they can describe:

* What containerized applications are running (and on which nodes)
* The resources available to those applications
* The policies around how those applications behave, such as restart policies, upgrades, and fault-tolerance

A PlaidCloud object is a "record of intent"--once you create the object, the PlaidCloud system will constantly work to ensure that object exists. By creating an object, you're effectively telling the PlaidCloud system what you want your cluster's workload to look like; this is your cluster's *desired state*.

To work with PlaidCloud objects--whether to create, modify, or delete them--you'll need to use the [PlaidCloud API](/docs/concepts/overview/Kubernetes-api/). When you use the `kubectl` command-line interface, for example, the CLI makes the necessary PlaidCloud API calls for you. You can also use the PlaidCloud API directly in your own programs using one of the [Client Libraries](/docs/reference/using-api/client-libraries/).

### Object Spec and Status

Almost every PlaidCloud object includes two nested object fields that govern
the object's configuration: the object *`spec`* and the object *`status`*.
For objects that have a `spec`, you have to set this when you create the object,
providing a description of the characteristics you want the resource to have:
its _desired state_.

The `status` describes the _current state_ of the object, supplied and updated
by the PlaidCloud system and its components. The PlaidCloud
{{< glossary_tooltip text="control plane" term_id="control-plane" >}} continually
and actively manages every object's actual state to match the desired state you
supplied.

For example: in PlaidCloud, a Deployment is an object that can represent an
application running on your cluster. When you create the Deployment, you
might set the Deployment `spec` to specify that you want three replicas of
the application to be running. The PlaidCloud system reads the Deployment
spec and starts three instances of your desired application--updating
the status to match your spec. If any of those instances should fail
(a status change), the PlaidCloud system responds to the difference
between spec and status by making a correction--in this case, starting
a replacement instance.

For more information on the object spec, status, and metadata, see the [PlaidCloud API Conventions](https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md).

### Describing a PlaidCloud object

When you create an object in PlaidCloud, you must provide the object spec that describes its desired state, as well as some basic information about the object (such as a name). When you use the PlaidCloud API to create the object (either directly or via `kubectl`), that API request must include that information as JSON in the request body. **Most often, you provide the information to `kubectl` in a .yaml file.** `kubectl` converts the information to JSON when making the API request.

Here's an example `.yaml` file that shows the required fields and object spec for a PlaidCloud Deployment:

{{< codenew file="application/deployment.yaml" >}}

One way to create a Deployment using a `.yaml` file like the one above is to use the
[`kubectl apply`](/docs/reference/generated/kubectl/kubectl-commands#apply) command
in the `kubectl` command-line interface, passing the `.yaml` file as an argument. Here's an example:

```shell
kubectl apply -f https://k8s.io/examples/application/deployment.yaml --record
```

The output is similar to this:

```
deployment.apps/nginx-deployment created
```

### Required Fields

In the `.yaml` file for the PlaidCloud object you want to create, you'll need to set values for the following fields:

* `apiVersion` - Which version of the PlaidCloud API you're using to create this object
* `kind` - What kind of object you want to create
* `metadata` - Data that helps uniquely identify the object, including a `name` string, `UID`, and optional `namespace`
* `spec` - What state you desire for the object

The precise format of the object `spec` is different for every PlaidCloud object, and contains nested fields specific to that object. The [PlaidCloud API Reference](https://plaidcloud.com/docs/reference/Kubernetes-api/) can help you find the spec format for all of the objects you can create using PlaidCloud.

For example, the reference for Pod details the [`spec` field](/docs/reference/Kubernetes-api/workload-resources/pod-v1/#PodSpec)
for a Pod in the API, and the reference for Deployment details the [`spec` field](/docs/reference/Kubernetes-api/workload-resources/deployment-v1/#DeploymentSpec) for Deployments.
In those API reference pages you'll see mention of PodSpec and DeploymentSpec. These names are implementation details of the Golang code that PlaidCloud uses to implement its API.


## {{% heading "whatsnext" %}}

* Learn about the most important basic PlaidCloud objects, such as [Pod](/docs/concepts/workloads/pods/).
* Learn about [controllers](/docs/concepts/architecture/controller/) in PlaidCloud.
* [Using the PlaidCloud API](/docs/reference/using-api/) explains some more API concepts.



