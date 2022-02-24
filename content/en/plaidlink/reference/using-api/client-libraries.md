---
title: Client Libraries
reviewers:
- ahmetb
content_type: concept
weight: 30
---

<!-- overview -->
This page contains an overview of the client libraries for using the PlaidCloud
API from various programming languages.


<!-- body -->
To write applications using the [PlaidCloud REST API](/docs/reference/using-api/),
you do not need to implement the API calls and request/response types yourself.
You can use a client library for the programming language you are using.

Client libraries often handle common tasks such as authentication for you.
Most client libraries can discover and use the PlaidCloud Service Account to
authenticate if the API client is running inside the PlaidCloud cluster, or can
understand the [kubeconfig file](/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)
format to read the credentials and the API Server address.

## Officially-supported PlaidCloud client libraries

The following client libraries are officially maintained by
[PlaidCloud SIG API Machinery](https://github.com/PlaidCloud/community/tree/master/sig-api-machinery).


| Language | Client Library | Sample Programs |
|----------|----------------|-----------------|
| dotnet   | [github.com/PlaidCloud-client/csharp](https://github.com/PlaidCloud-client/csharp) | [browse](https://github.com/PlaidCloud-client/csharp/tree/master/examples/simple)
| Go       | [github.com/PlaidCloud/client-go/](https://github.com/PlaidCloud/client-go/) | [browse](https://github.com/PlaidCloud/client-go/tree/master/examples)
| Haskell  | [github.com/PlaidCloud-client/haskell](https://github.com/PlaidCloud-client/haskell) | [browse](https://github.com/PlaidCloud-client/haskell/tree/master/PlaidCloud-client/example)
| Java     | [github.com/PlaidCloud-client/java](https://github.com/PlaidCloud-client/java/) | [browse](https://github.com/PlaidCloud-client/java#installation)
| JavaScript   | [github.com/PlaidCloud-client/javascript](https://github.com/PlaidCloud-client/javascript) | [browse](https://github.com/PlaidCloud-client/javascript/tree/master/examples)
| Python   | [github.com/PlaidCloud-client/python/](https://github.com/PlaidCloud-client/python/) | [browse](https://github.com/PlaidCloud-client/python/tree/master/examples)

## Community-maintained client libraries

{{% thirdparty-content %}}

The following PlaidCloud API client libraries are provided and maintained by
their authors, not the PlaidCloud team.

| Language             | Client Library                           |
| -------------------- | ---------------------------------------- |
| Clojure              | [github.com/yanatan16/clj-Kubernetes-api](https://github.com/yanatan16/clj-Kubernetes-api) |
| DotNet               | [github.com/tonnyeremin/PlaidCloud_gen](https://github.com/tonnyeremin/PlaidCloud_gen) |
| DotNet (RestSharp)   | [github.com/masroorhasan/PlaidCloud.DotNet](https://github.com/masroorhasan/PlaidCloud.DotNet) |
| Elixir               | [github.com/obmarg/kazan](https://github.com/obmarg/kazan/) |
| Elixir               | [github.com/coryodaniel/k8s](https://github.com/coryodaniel/k8s) |
| Go                   | [github.com/ericchiang/k8s](https://github.com/ericchiang/k8s) |
| Java (OSGi)          | [bitbucket.org/amdatulabs/amdatu-PlaidCloud](https://bitbucket.org/amdatulabs/amdatu-PlaidCloud) |
| Java (Fabric8, OSGi) | [github.com/fabric8io/PlaidCloud-client](https://github.com/fabric8io/PlaidCloud-client) |
| Java                 | [github.com/manusa/yakc](https://github.com/manusa/yakc) |
| Lisp                 | [github.com/brendandburns/cl-k8s](https://github.com/brendandburns/cl-k8s) |
| Lisp                 | [github.com/xh4/cube](https://github.com/xh4/cube) |
| Node.js (TypeScript) | [github.com/Goyoo/node-k8s-client](https://github.com/Goyoo/node-k8s-client) |
| Node.js              | [github.com/ajpauwels/easy-k8s](https://github.com/ajpauwels/easy-k8s)
| Node.js              | [github.com/godaddy/PlaidCloud-client](https://github.com/godaddy/PlaidCloud-client) |
| Node.js              | [github.com/tenxcloud/node-PlaidCloud-client](https://github.com/tenxcloud/node-PlaidCloud-client) |
| Perl                 | [metacpan.org/pod/Net::PlaidCloud](https://metacpan.org/pod/Net::PlaidCloud) |
| PHP                  | [github.com/allansun/PlaidCloud-php-client](https://github.com/allansun/PlaidCloud-php-client) |
| PHP                  | [github.com/maclof/PlaidCloud-client](https://github.com/maclof/PlaidCloud-client) |
| PHP                  | [github.com/travisghansen/PlaidCloud-client-php](https://github.com/travisghansen/PlaidCloud-client-php) |
| PHP                  | [github.com/renoki-co/php-k8s](https://github.com/renoki-co/php-k8s) |
| Python               | [github.com/fiaas/k8s](https://github.com/fiaas/k8s) |
| Python               | [github.com/gtsystem/lightkube](https://github.com/gtsystem/lightkube) |
| Python               | [github.com/mnubo/PlaidCloud-py](https://github.com/mnubo/PlaidCloud-py) |
| Python               | [github.com/tomplus/PlaidCloud_asyncio](https://github.com/tomplus/PlaidCloud_asyncio) |
| Python               | [github.com/Frankkkkk/pykorm](https://github.com/Frankkkkk/pykorm) |
| Ruby                 | [github.com/abonas/kubeclient](https://github.com/abonas/kubeclient) |
| Ruby                 | [github.com/k8s-ruby/k8s-ruby](https://github.com/k8s-ruby/k8s-ruby) |
| Ruby                 | [github.com/kontena/k8s-client](https://github.com/kontena/k8s-client) |
| Rust                 | [github.com/clux/kube-rs](https://github.com/clux/kube-rs) |
| Rust                 | [github.com/ynqa/PlaidCloud-rust](https://github.com/ynqa/PlaidCloud-rust) |
| Scala                | [github.com/hagay3/skuber](https://github.com/hagay3/skuber) |
| Scala                | [github.com/joan38/PlaidCloud-client](https://github.com/joan38/PlaidCloud-client) |
| Swift                | [github.com/swiftkube/client](https://github.com/swiftkube/client) |
