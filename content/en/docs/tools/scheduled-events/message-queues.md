---
title: Message Queues
slug: message-queues
description: Create and Manage 'vHost' Message Queues
date: 2022-01-25T07:39:49
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


# vHost Queues


**To reach and view vHost Queues:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the queues icon of the desired vHost

This will open the **Queues Table** which displays the list of queues and other important information related to the vHost, including its message state, consumers, and rate of message processing.



## Creating Queues


**To create a queue:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the queues icon of the desired vHost
6. Click “Add Queue”

This will open a form where you can provide a name, durability level, and determine if the queue should be deleted when no consumers are present.



Durability is useful if a message needs to be retained in the event of a system failure or restart. If you choose not to create a durable queue, then the message will be lost after a restart. Although durability is useful, it is not always desired.



Creating a durable queue results in a slightly slower process because each message must be stored in permanent storage. We suggest then that you only create a durable queue when the message is critical and use non-durable queues when a message is executed right away or is not critical.



## Deleting Queues


**To delete a queue:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the queues icon of the desired vHost
6. Click the delete icon of the desired queue

***Note***: When a queue is deleted, any consumers listening on the queue will be disconnected from the queue.



## Purging a Queue


Purging a queue will delete all messages in that queue.



***Note***: Messages that have already been acknowledged will not be purged because at least one member has received and marked the message as incomplete.



**To purge a queue:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the queues icon of the desired vHost
6. Click the purge icon of the desired queue
7. Click “Purge Queue”
