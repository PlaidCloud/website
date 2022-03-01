---
title: func.substring
slug: func-substring
description: The SUBSTRING() extracts a substring with a specified length starting from a location in an input string
date: 2022-02-07T10:25:58
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Syntax



```
func.substring(string, start, length)
```


## Examples



```
Example 1: Takes the first 5 characters from a 9 digit postal code func.substring(table.ship_to_postal_code, 1, 5)  
  
func.substring('Plaidcloud_string', 1,10) --> Plaidcloud
```
