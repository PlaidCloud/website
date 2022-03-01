---
title: or_
slug: or
description: Checks if any conditions are met
date: 2022-01-25T07:39:47
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


The or\_ operator allows checking two or more conditions to determine if the evaluation is true or false.




---

## Examples


**Example 1**


This example checks if the `period` is any of the three specified dates.



```
or_(  
    table.period == '2020_10',  
    table.period == '2020_11',  
    table.period == '2020_12'  
)
```


**Example 2**


This example is checking if `order_reason_Include` is `null` or has the word `KEEP` as a value.



```
or_(  
    table.order_reason_Include == 'KEEP',  
    table.order_reason_Include.is_(None)  
)
```

