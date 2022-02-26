---
title: func.ST_RelateMatch
slug: func-st-relatematch
description: Tests if a Dimensionally Extended 9-Intersection Model (DE-9IM) intersectionMatrix value satisfies an intersectionMatrixPattern
date: 2022-01-31T10:03:41
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


# Description


PlaidCloud expressions and filters provide use of most non-administrative PostGIS methods. PostGIS methods are accessed by prefixing the standard method name with `func.`.



# Examples


## SQL



```
ST_RelateMatch(text intersectionMatrix, text intersectionMatrixPattern);
```


## PlaidCloud



```
func.ST_RelateMatch(text intersectionMatrix, text intersectionMatrixPattern);
```


## References


PostGIS Official Documentation for this method can be found [here](https://postgis.net/docs/manual-3.1/ST_RelateMatch.html).



Additional capabilities and usage examples can be found in the PostGIS documentation

