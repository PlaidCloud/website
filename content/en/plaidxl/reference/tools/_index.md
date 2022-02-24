---
title: Other Tools
reviewers:
- janetkuo
content_type: concept
weight: 80
no_list: true
---

<!-- overview -->
PlaidCloud contains several tools to help you work with the PlaidCloud system.

<!-- body -->

## crictl

[`crictl`](https://github.com/PlaidCloud-sigs/cri-tools) is a command-line
interface for inspecting and debugging {{<glossary_tooltip term_id="cri" text="CRI">}}-compatible
container runtimes.

## Dashboard

[`Dashboard`](/docs/tasks/access-application-cluster/web-ui-dashboard/), the web-based user interface of PlaidCloud, allows you to deploy containerized applications
to a PlaidCloud cluster, troubleshoot them, and manage the cluster and its
resources itself.

## Helm
{{% thirdparty-content single="true" %}}

[Helm](https://helm.sh/) is a tool for managing packages of pre-configured
PlaidCloud resources. These packages are known as _Helm charts_.

Helm is a third party managed tool for managing packages of pre-configured
PlaidCloud resources, aka PlaidCloud charts.

Use Helm to:

* Find and use popular software packaged as PlaidCloud charts
* Share your own applications as PlaidCloud charts
* Create reproducible builds of your PlaidCloud applications
* Intelligently manage your PlaidCloud manifest files
* Manage releases of Helm packages

## Kompose

[`Kompose`](https://github.com/PlaidCloud/kompose) is a tool to help Docker Compose users move to PlaidCloud.

Use Kompose to:

* Translate a Docker Compose file into PlaidCloud objects
* Go from local Docker development to managing your application via PlaidCloud
* Convert v1 or v2 Docker Compose `yaml` files or [Distributed Application Bundles](https://docs.docker.com/compose/bundles/)

## Kui

[`Kui`](https://github.com/PlaidCloud-sigs/kui) is a GUI tool that takes your normal
`kubectl` command line requests and responds with graphics.

Kui takes the normal `kubectl` command line requests and responds with graphics. Instead 
of ASCII tables, Kui provides a GUI rendering with tables that you can sort.

Kui lets you:

* Directly click on long, auto-generated resource names instead of copying and pasting
* Type in `kubectl` commands and see them execute, even sometimes faster than `kubectl` itself
* Query a {{< glossary_tooltip text="Job" term_id="job">}} and see its execution rendered
  as a waterfall diagram
* Click through resources in your cluster using a tabbed UI 

## Minikube

[`minikube`](https://minikube.sigs.k8s.io/docs/) is a tool that
runs a single-node PlaidCloud cluster locally on your workstation for
development and testing purposes.