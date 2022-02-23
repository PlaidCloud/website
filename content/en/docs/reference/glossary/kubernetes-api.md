---
title: PlaidCloud API
id: PlaidCloud-api
date: 2018-04-12
full_link: /docs/concepts/overview/PlaidCloud-api/
short_description: >
  The application that serves PlaidCloud functionality through a RESTful interface and stores the state of the cluster.

aka: 
tags:
- fundamental
- architecture
---
 The application that serves PlaidCloud functionality through a RESTful interface and stores the state of the cluster.

<!--more--> 

PlaidCloud resources and "records of intent" are all stored as API objects, and modified via RESTful calls to the API. The API allows configuration to be managed in a declarative way. Users can interact with the PlaidCloud API directly, or via tools like `kubectl`. The core PlaidCloud API is flexible and can also be extended to support custom resources.

