---
title: func.ST_Rotate
slug: func-st-rotate
description: Rotates geometry rotRadians counter-clockwise about the origin point
date: 2022-01-31T17:33:07
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


PlaidCloud expressions and filters provide use of most non-administrative PostGIS methods. PostGIS methods are accessed by prefixing the standard method name with `func.`.



## Examples


### SQL



```
ST_Rotate(geometry geomA, float rotRadians);
```


### PlaidCloud



```
func.ST_Rotate(geometry geomA, float rotRadians);
```


### References


PostGIS Official Documentation for this method can be found [here](https://postgis.net/docs/manual-3.1/ST_Rotate.html).



Additional capabilities and usage examples can be found in the PostGIS documentation

