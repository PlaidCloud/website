---
title: Path
slug: path
description: Performs regular pattern matching over a sequence of rows
date: 2022-01-25T07:40:19
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


PlaidCloud expressions and filters provide use of most non-administrative Apache MADLib methods. Apache MADLib methods are accessed by prefixing the standard method name with `func.madlib.`.



## In SQL



```
madlib.path('eventlog', 'path_output', 'session_id', 'event_timestamp ASC', 'buy:=page=''CHECKOUT''', '(buy)', 'sum(revenue) as checkout_rev', TRUE)
```


## In PlaidCloud Expressions & Filters



```
func.madlib.path('eventlog', 'path_output', 'session_id', 'event_timestamp ASC', "buy:=page='CHECKOUT'", '(buy)', 'sum(revenue) as checkout_rev', TRUE)
```


## External References


Apache MADLib Official Documentation for this method can be found [here](https://madlib.apache.org/docs/latest/group__grp__path.html).



Additional capabilities and usage examples can be found in the Apache MADLib documentation.

