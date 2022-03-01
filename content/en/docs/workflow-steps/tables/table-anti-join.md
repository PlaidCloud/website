---
title: Table Anti Join
slug: table-anti-join
description: This function provides an unmatched set of data between two tables
date: 2022-01-25T07:39:50
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


Table Anti Join provides the unmatched set of items between two tables. This will return the list of items in the first table without matches in the second table. This can be quite useful for determining which records are present in one table but not another.



This operation could be accomplished by using outer joins and filtering on null values for the join; however, the Anti Join transform will perform this in a more efficient and obvious way.



## Table A Data Selection


### Table Source


Specify the source data table by selecting it from the dropdown menu.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



### Duplicates


There is a checkbox option to use **Distinct Rows Only**. This is especially helpful in cases where duplicates may exist but are not desired. As experienced modelers know, having non-distinct data in an SQL join can increase expected record count significantly.



Additionally, there is standard functionality to **Report Duplicates in Table** elsewhere.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.
{{< /caution >}}



### Source Columns and Replacements


Specify any columns to be included in the Anti Join here. Selecting the **Inspect Source** and **Populate Source Mapping Table** buttons will make these columns available for the join operation.



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



## Table B Data Selection


### Table Source


Specify the source data table by selecting it from the dropdown menu.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



### Duplicates


There is a checkbox option to use **Distinct Rows Only**. This is especially helpful in cases where duplicates may exist, but are not desired. As experienced modelers know, having non-distinct data in an SQL join can increase expected record count significantly.



Additionally, there is standard functionality to **Report Duplicates in Table** elsewhere. For more details on this capability, see details here:



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.
{{< /caution >}}



### Source Columns and Replacements


Specify any columns to be included in the Anti Join here. Selecting the **Inspect Source** and **Populate Source Mapping Table** buttons will make these columns available for the join operation.



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



## Table Output


### Target Table


Specify the **Target Table** name by either selecting an existing data table from the dropdown menu or typing a new data table name into the same menu. By default, the **Target Table** is automatically populated with the specific transform’s name. Note that data tables must follow Linux naming conventions. As such, we recommend that names only consist of alphanumeric characters. Analyze will automatically scrub any invalid characters from the name.



### Join Map


Specify join conditions. Using the **Guess** button will find all matching columns from both **Table A** as well as **Table B**. To add additional columns manually, right click anywhere in the section and select either **Insert Row** or **Append Row**, to add a row prior to the currently selected row or to add a row at the end, respectively. Then, type the column names to match from **Table A** to **Table B**. To remove a field from the **Join Map**, simply right-click and select **Delete**.



### Target Output Columns


Specify the columns to appear in the target data table. Selecting the **Propagate** button will insert all columns listed in the **Source Columns and Replacements** section of both **Table A** and **Table B**. Any columns included in the **Join Map** will only be listed a single time.



To add additional columns manually, right click anywhere in the section and select either **Insert Row** or **Append Row**, to add a row prior to the currently selected row or to add a row at the end, respectively. Then, type the column name. To remove a field, simply right-click and select **Delete**.



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples






### Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop



