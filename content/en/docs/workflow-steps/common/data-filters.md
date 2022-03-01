---
title: Data Filters
slug: data-filters
description: Filter out specific data to maximize workflow flexibility
date: 2022-01-25T07:39:52
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description



To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows of the source so the remaining operations are performed on a smaller data set.



## Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.



## Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table, which will contain all of the duplicate records.

{{< caution >}}
This will **not** remove the duplicate items from the target data table. To *remove* duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.
{{< /caution >}}




## Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples





