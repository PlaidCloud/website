---
title: Message Queue Virtual Host
slug: message-queue-virtual-host
description: Create and Manage Virtual Hosts (vHost) for message queues
date: 2022-01-25T07:39:49
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


In order to ease the transition between new applications, it may sometimes be necessary for business teams to coordinate services and processes using services that cannot communicate in real-time. PlaidCloud provides a high performance messaging queue to handle asynchronous communication, with a wide range of delivery options, including:


* Direct exchange
* Fanout exchange
* Topic exchange
* Headers exchange

This function is provided by RabbitMQ clusters and is not intended to replace internal message queueing systems, although PlaidCloud’s message queue is capable of doing so.



Click here (<https://www.rabbitmq.com/tutorials/tutorial-two-python.html>) for additional information from RabbitMQ.



## Virtual Hosts (vHosts)


Virtual Hosts (vHosts) can be thought of as small, isolated message servers used for specific purposes such as queues, exchanges, and bindings. PlaidCloud uses vHosts to form its foundation for the message broker infrastructure.



**To view current vHosts:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”

This will open the **vHosts Table** in the workspace, which includes vHost information and access to Queues, Permissions, Bindings, and Exchanges related to the vHost.



### Creating vHosts


**To create a vHost:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click “Add vHost”
6. Name the vHost for future referencing
7. Click “Create”

Once the vHost is created, it will be tagged with its reference to a workspace identifier. For example, if you create a vHost with the name of ‘super’ and its identifier is 890, the actual name of the user will be ‘cloud_890_super’. This allows for unique vHosts without constant name collisions.



### Deleting vHosts


**To delete a vHost:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the delete icon
6. Click “Delete” again

{{< note >}}
Deleting a vHost will delete all of its associated permissions, bindings, queues, and exchanges.
{{< /note >}}


  


