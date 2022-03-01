---
title: and_
slug: and
description: Checks if all conditions are met
date: 2022-01-25T07:39:47
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


The and\_ operator allows checking if two or more conditions are all met.




---

## Examples


**Example 1**


This example checks if the `period` is any of the three specified dates.



```
and_(  
    table.color == 'green',  
    table.shape == 'circle',  
    table.price >= 1.25  
)
```


**Example 2**


This example is checking if to ensure the `origin_plant` is not one of the values specified. This is using the `!=` expression.



```
and_(  
    table.origin_plant != '5013',  
    table.origin_plant != '5026',  
    table.origin_plant != '5120',  
    table.origin_plant != '5287',  
    table.origin_plant != '5161',  
    table.origin_plant != '5192'  
)
```

Alternatively, for reference, the above check could be written using the `not_` and `or_` operators like this:



```
not_(  
    or_(  
        table.origin_plant == '5013',  
        table.origin_plant == '5026',  
        table.origin_plant == '5120',  
        table.origin_plant == '5287',  
        table.origin_plant == '5161',  
        table.origin_plant == '5192'  
    )  
)
```
