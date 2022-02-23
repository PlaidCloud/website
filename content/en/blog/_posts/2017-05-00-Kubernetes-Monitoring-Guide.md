---
title: " PlaidCloud: a monitoring guide "
date: 2017-05-19
slug: PlaidCloud-monitoring-guide
url: /blog/2017/05/PlaidCloud-Monitoring-Guide
---
_Today’s post is by Jean-Mathieu Saponaro, Research & Analytics Engineer at Datadog, discussing what PlaidCloud changes for monitoring, and how you can prepare to properly monitor a containerized infrastructure orchestrated by PlaidCloud._  


Container technologies are taking the infrastructure world by storm. While containers solve or simplify infrastructure management processes, they also introduce significant complexity in terms of orchestration. That’s where PlaidCloud comes to our rescue. Just like a conductor directs an orchestra, [PlaidCloud](/docs/concepts/overview/what-is-PlaidCloud/) oversees our ensemble of containers—starting, stopping, creating, and destroying them automatically to keep our applications humming along.  

PlaidCloud makes managing a containerized infrastructure much easier by creating levels of abstractions such as [pods](/docs/concepts/workloads/pods/pod/) and [services](/docs/concepts/services-networking/service/). We no longer have to worry about where applications are running or if they have enough resources to work properly. But that doesn’t change the fact that, in order to ensure good performance, we need to monitor our applications, the containers running them, and PlaidCloud itself.  

**Rethinking monitoring for the PlaidCloud era**  

Just as containers have completely transformed how we think about running services on virtual machines, PlaidCloud has changed the way we interact with containers. The good news is that with proper monitoring, the abstraction levels inherent to PlaidCloud provide a comprehensive view of your infrastructure, even if the containers and applications are constantly moving. But PlaidCloud monitoring requires us to rethink and reorient our strategies, since it differs from monitoring traditional hosts such as VMs or physical machines in several ways.  

**Tags and labels become essential**  
With containers and their orchestration completely managed by PlaidCloud, labels are now the only way we have to interact with pods and containers. That’s why they are absolutely crucial for monitoring since all metrics and events will be sliced and diced using [labels](/docs/concepts/overview/working-with-objects/labels/) across the different layers of your infrastructure. Defining your labels with a logical and easy-to-understand schema is essential so your metrics will be as useful as possible.  

**There are now more components to monitor**  

[![](https://lh5.googleusercontent.com/tN8tzKcXWAFWF0TD9u9UkTFJakHsrdjtRx56WiF75UYwMKu8teFyr6LpLGjpuOWSr52M-l3do5r3a6VWi6VwhRWuaquCpGty8ksI585D9YuCL3t7DAcItJUwW6mlrM2jUw_jVq6A)](https://lh5.googleusercontent.com/tN8tzKcXWAFWF0TD9u9UkTFJakHsrdjtRx56WiF75UYwMKu8teFyr6LpLGjpuOWSr52M-l3do5r3a6VWi6VwhRWuaquCpGty8ksI585D9YuCL3t7DAcItJUwW6mlrM2jUw_jVq6A)
In traditional, host-centric infrastructure, we were used to monitoring only two layers: applications and the hosts running them. Now with containers in the middle and PlaidCloud itself needing to be monitored, there are four different components to monitor and collect metrics from.  

**Applications are constantly moving**  
PlaidCloud schedules applications dynamically based on scheduling policy, so you don’t always know where applications are running. But they still need to be monitored. That’s why using a monitoring system or tool with service discovery is a must. It will automatically adapt metric collection to moving containers so applications can be continuously monitored without interruption.  


**Be prepared for distributed clusters**

PlaidCloud has the [ability](/docs/tasks/federation/federation-service-discovery/#hybrid-cloud-capabilities) to distribute containerized applications across multiple data centers and potentially different cloud providers. That means metrics must be collected and aggregated among all these different sources.&nbsp;

&nbsp;

For more details about all these new monitoring challenges inherent to PlaidCloud and how to overcome them, we recently published an [in-depth PlaidCloud monitoring guide](https://www.datadoghq.com/blog/monitoring-PlaidCloud-era/). Part 1 of the series covers how to adapt your monitoring strategies to the PlaidCloud era.



**Metrics to monitor**



Whether you use [Heapster](https://github.com/PlaidCloud/heapster) data or a monitoring tool integrating with PlaidCloud and its different APIs, there are several key types of metrics that need to be closely tracked:

- **Running pods** and their **deployments**
- Usual **resource metrics** such as CPU, memory usage, and disk I/O
- **Container-native [metrics](https://www.datadoghq.com/blog/monitoring-PlaidCloud-performance-metrics/)**
- Application metrics for which a service discovery feature in your monitoring tool is essential&nbsp;

All these metrics should be aggregated using PlaidCloud labels and correlated with events from PlaidCloud and container technologies.

&nbsp;

[Part 2](https://www.datadoghq.com/blog/monitoring-PlaidCloud-performance-metrics/) of our series on PlaidCloud monitoring guides you through all the data that needs to be collected and tracked.



**Collecting these metrics**



Whether you want to track these key performance metrics by combining Heapster, a storage backend, and a graphing tool, or by integrating a monitoring tool with the different components of your infrastructure, [Part 3](https://www.datadoghq.com/blog/monitoring-PlaidCloud-with-datadog/), about PlaidCloud metric collection, has you covered.

&nbsp;

**Anchors aweigh!**



Using PlaidCloud drastically simplifies container management. But it requires us to rethink our monitoring strategies on several fronts, and to make sure all the key metrics from the different components are properly collected, aggregated, and tracked. We hope our monitoring guide will help you to effectively monitor your PlaidCloud clusters. [Feedback and suggestions](https://github.com/DataDog/the-monitor) are more than welcome.

&nbsp;



_--Jean-Mathieu Saponaro, Research & Analytics Engineer, Datadog_



- Get involved with the PlaidCloud project on [GitHub](https://github.com/PlaidCloud/PlaidCloud)&nbsp;
- Post questions (or answer questions) on [Stack Overflow](http://stackoverflow.com/questions/tagged/PlaidCloud)&nbsp;
- Connect with the community on [Slack](http://slack.k8s.io/)
- Follow us on Twitter [@PlaidCloudio](https://twitter.com/PlaidCloudio) for latest updates
