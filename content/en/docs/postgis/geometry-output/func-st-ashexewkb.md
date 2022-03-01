---
title: func.ST_AsHEXEWKB
slug: func-st-ashexewkb
description: Returns a Geometry in HEXEWKB format (as text) using either little-endian (NDR) or big-endian (XDR) encoding
date: 2022-01-29T19:08:44
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
ST_AsHEXEWKB(geometry g1);
```


### PlaidCloud



```
func.ST_AsHEXEWKB(geometry g1);
```


### References


PostGIS Official Documentation for this method can be found [here](https://postgis.net/docs/manual-3.1/ST_AsHEXEWKB.html).



Additional capabilities and usage examples can be found in the PostGIS documentation

