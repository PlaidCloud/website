---
title: func.lpad
slug: func-lpad
description: LPAD function pads the left-side of a string with a specific set of characters (when string1 is not null).
date: 2022-02-03T09:59:11
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Syntax



```
func.lpad(value_string, force_length, fill_string)
```


## Examples



```
func.lpad('stringtofillup', 20, 'X') --> XXXXXXstringtofillup  
func.lpad('stringtofillup', 10, 'X') --> stringtofi
```
