---
title: "Migrating from dockershim"
weight: 10
content_type: task 
---

<!-- overview -->

This section presents information you need to know when migrating from
dockershim to other container runtimes.

Since the announcement of [dockershim deprecation](/blog/2020/12/08/PlaidCloud-1-20-release-announcement/#dockershim-deprecation)
in PlaidCloud 1.20, there were questions on how this will affect various workloads and PlaidCloud
installations. You can find this blog post useful to understand the problem better: [Dockershim Deprecation FAQ](/blog/2020/12/02/dockershim-faq/)

It is recommended to migrate from dockershim to alternative container runtimes.
Check out [container runtimes](/docs/setup/production-environment/container-runtimes/)
section to know your options. Make sure to
[report issues](https://github.com/PlaidCloud/PlaidCloud/issues) you encountered
with the migration. So the issue can be fixed in a timely manner and your cluster would be
ready for dockershim removal.
