---
title: Message Queue Exchanges, Bindings and Permissions
slug: message-queue-exchanges-bindings-and-permissions
description: Create and manage your own exchanges and viewership controls for message queues
date: 2022-01-25T07:39:49
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


# vHost Exchanges


**To view exchanges:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the exchanges icon of the desired vHost

This will open the **Exchanges Table** which displays the list of all exchanges related to the vHost.



## Creating Exchanges


**To create an exchange:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the exchanges icon of the desired vHost
6. Click “Add Exchange”
7. Complete the required fields
8. Click “Submit”

## Deleting Exchanges


**To delete an exchange:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the exchanges icon of the desired vHost
6. Click the delete icon of the desired exchange
7. Click “Delete” again

# vHost Bindings


**To view bindings:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the bindings icon of the desired vHost

This will open the **Bindings Table**, which displays the list of bindings and other important information related to the vHost.



## Creating Bindings


**To create a binding:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the bindings icon of the desired vHost
6. Click “Add Binding”
7. Complete the desired fields
8. Click “Submit”

## Deleting Bindings


**To delete bindings:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the bindings icon of the desired vHost
6. Click the delete icon of the desired binding
7. Click “Delete” again

# vHost Permissions


**To view permissions:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the permissions icon of the desired vHost

This will open the **Permissions Table**, which displays the list of users and their permissions related to the vHost.



## Creating Permissions


**To create a permission:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the permissions icon of the desired vHost
6. Click “Add Permissions”
7. Complete the required fields
8. Click “Submit”

## Deleting Permissions


**To delete permissions:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “vHosts”
5. Click the permissions icon of the desired vHost
6. Click the delete icon of the desired permission
7. Click “Delete” again

# Users


In order to access messages in the message queue, you must first set up users. PlaidCloud allows you to create an unlimited number of users in order to suit your needs.



***Note*:** Because users can be granted permission to access multiple vHosts without needing different access levels, it is unnecessary to create one user for every vHost.



**To view users who may access vHost and messaging services:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “Users”

This will open the **User Table**, which displays users currently in the workspace and their admin level permissions.



## Creating Users


**To create a new user:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “Users”
5. Click “Add User”
6. Complete the required fields
7. Click “Create”

***Note***: You cannot edit any of the settings, including the password, after creating the user.



## Controlling User Access


The Admin Level setting provides the user with different privileges. PlaidCloud provides three levels of access:


* No Admin Access
* Management Admin Access
* Monitoring Admin Access

**No Admin Access** provides no administrative access but allows the user to utilize all other permission based access.



**Management Admin Access** provides full permission based access, as well as the following:


* List virtual hosts to which they can log in
* View all queues, exchanges, and bindings in “their” virtual hosts
* View and close their own channels and connections
* View “global” statistics covering all their virtual hosts, including activity by other users

**Monitoring Admin Access** provides everything “Management Admin Access” provides, as well as the following:


* List all virtual hosts, including ones they could not log into via AMQP
* View other users’ connections and channels
* View node-level data such as memory use and clustering
* View truly global statistics for all virtual hosts

## Deleting Users


**To delete a user:**


1. Open Analyze
2. Select the “Tools” menu
3. Hover over “Queueing” in the dropdown menu
4. Click “Users”
5. Click the delete icon of the desired user 


	* Click “Delete” again

***Note***: Deleting a user will automatically remove all permissions granted to the user on all vHosts.

