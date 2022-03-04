---
title: Getting Started
slug: getting-started
description: Get connected and run APIs from command line or another application
date: 2022-01-25T07:39:47
---


PlaidCloud uses standard JSON-RPC requests and can be used with any application that can perform those requests.


To make things easier, a Python package is available to simplify the connection and API running process.


## Required Installation

From a terminal run the following command:

```bash
pip install plaidcloud-rpc
```


## Using the SimpleRPC Object to Make a Request

To make a request using the `plaidcloud-rpc` package use the `SimpleRPC` object.

```python
from plaidcloud.rpc.connection.jsonrpc import SimpleRPC  
  
auth_token = "Your PlaidCloud Auth Token" # See Obtaining Token below  
endpoint_uri = "plaidcloud.com" # or plaidcloud.net  
rpc = SimpleRPC(auth_token, endpoint_uri)
```

Once you have the `SimpleRPC` object instantiated you can then issue RPC request to PlaidCloud. This example requests the meta data for a table.

```python
table = rpc.analyze.table.table(  
            project_id=project_id,  
            table_id=table_id  
        )
```

## What APIs are Available?

There are many APIs available for use that control nearly every aspect of PlaidCloud. All of the APIs, the inputs, and expected outputs are documented in the [APIs documentation](https://api.plaidcloud.com).

## Obtaining an OAuth Token

OAuth tokens are generated from the PlaidCloud app. To view the list of current OAuth tokens assigned to you and generate new ones, navigate to `Analyze > Tools > Registered Systems`.

Once there you can view any existing tokens or choose to create a new one.

