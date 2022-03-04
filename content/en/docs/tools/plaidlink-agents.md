---
title: PlaidLink Agents
slug: plaidlink-agents
description: Create and manage remote access using lightweight agents
date: 2022-01-25T07:39:49
---


## Description


Sometimes it’s necessary and desired to access data or run processes from a remote system that does not allow external access. This is common in enterprise environments behind firewalls. PlaidCloud allows this ability by using PlaidLink, which enables remote systems access behind a firewall or where direct access from PlaidCloud is not desired.



PlaidLink uses an agent-based system. This means that an agent, the remote user, is installed on a system inside the firewall or other restricted area. The agent can then connect to PlaidCloud by using an outbound initiation process over a secure HTTPS websocket connection. It is as secure as any other encrypted web connection and usually does not require you to open non-standard ports. Before gaining access, the agent must identify itself by sending its agent identifier. From this, if the agent has a successful authentication process, the agent is granted access to the approved operations.



PlaidLink can be installed on Windows, Unix, and Linux systems and can run under low privilege users. On Windows systems, PlaidLink can operate as a Windows Service with full control from the Service panel. On linux or unix systems, it can run as a deamon process.



## Managing Agents


**To manage agents:**


1. Open Analyze
2. Select “Tools”
3. Click “PlaidLink Agents”

This brings you to the **PlaidLink Agents Table** where you can view, modify, and obtain credentials for the list of available agents.



## Creating an Agent


**To create an agent:**


1. Open Analyze
2. Select “Tools”
3. Click “PlaidLink Agents”
4. Click “Add PlaidLink Agent”
5. Complete the required fields
6. Click “Create”
7. Assign the agent to the necessary security groups to access resources needed to perform their job


	* If the agent is not assigned, they will not have access
8. Assign the agent to the necessary Document accounts to access documents needed to perform their job


	* If the agent is not assigned, they will not have access

{{< note >}}
Any information not present on the new agent form will be automatically generated.
{{< /note >}}



## Obtaining Agent Credentials


To configure PlaidLink agents on the remote system, you must first obtain the agent’s identifying information in order to maintain security. This information includes both a public and a private key.



**To obtain these keys:**


1. Open Analyze
2. Select “Tools”
3. Click “PlaidLink Agents”
4. Click the edit icon

This will open a form where you can view the public and private key values.



Please see the PlaidLink installation documentation if you need to install the agent: :*doc:’../../../plaidlink/getting_started.rst’*



## Regenerating Agent Credentials


It is a good idea to periodically regenerate the public and private keys and update the configuration of remote systems in order to maintain security.



**To regenerate the credentials:**


1. Open Analyze
2. Select “Tools”
3. Click “PlaidLink Agents”
4. Click the regenerate icon

Once the credentials have been regenerated, they can be obtained in the same way a new agent’s credentials are obtained (described above).



## Enabling and Disabling an Agent


**To disable an agent:**


1. Open Analyze
2. Select “Tools”
3. Click “PlaidLink Agents”
4. Uncheck the “Active” checkbox

{{< note >}}
When an agent is not marked as active, remote systems will not be able to connect using those agent credentials.
{{< /note >}}



## Running Multiple Agents


PlaidLink is designed to allow operation of multiple agents using a single service installation. Such a streamlined installation system permits one install to handle agents from multiple workspaces and / or agents with different levels of permissions for task execution.



To enable multiple agents, you simply add the agent credentials to the PlaidLink configuration file.

