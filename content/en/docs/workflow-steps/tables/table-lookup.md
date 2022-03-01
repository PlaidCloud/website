---
title: Table Lookup
slug: table-lookup
description: Similar to Microsoft Excel, this workflow function also increases process performance
date: 2022-01-25T07:39:49
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


If you are a regular user of the vlookup function in Microsoft Excel, the Table Lookup transform should feel very familiar. It’s used to perform essentially the same function. Unlike the Microsoft Excel version, the PlaidCloud Analyze Table Lookup transform offers greater flexibility, especially allowing for matching on and returning multiple columns.



## Source and Target Parameters


### Source and Target


To establish the source and target, first select the data table to be exported from the 
dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.



### Lookup Table Source


Select the Lookup Table from the dropdown list. This list includes all *Project* and *Workflow* data tables.



### Select Subset of Lookup Data


Any valid Python expression is acceptable to subset the data. Please see the following section for more details and examples: [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions)



### Lookup Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (row for column header is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



### Table Data Selection


The Table Data Selection tab is used to map columns from the source data table to the target data table. All source columns on the left side of the window are automatically mapped to the target data table depicted on the right side of the window. Using the **Inspect Source** menu button, there are a few additional ways to map columns from source to target:


* Populate Both Mapping Tables: Propagates all values from the source data table into the target data table. This is done by default.
* Populate Source Mapping Table Only: Maps all values in the source data table only. This is helpful when modifying an existing workflow when source column structure has changed.
* Populate Target Mapping Table Only: Propagates all values into the target data table only.

In addition to each of these options, each choice offers the ability to preview the source data.



If the source and target column options aren’t enough, other columns can be added into the target data table in several different ways:


* **Propagate All** will insert all source columns into the target data table, whether they already existed or not.
* **Propagate Selected** will insert selected source column(s) only.
* Right click on target side and select **Insert Row** to insert a row immediately above the currently selected row.
* Right click on target side and select **Append Row** to insert a row at the bottom (far right) of the target data table.


{{< warning >}}
Selecting **Propagate All** may effectively create a duplicate of every column. Analyze does not check to see if the columns are already mapped. Make sure duplicate column names do not exist.
{{< /warning >}}




To delete columns from the target data table, select the desired column(s), then right click and select **Delete**.



To rearrange columns in the target data table, select the desired column(s), then right click and select **Move to Top**, **Move Up**, **Move Down**, or **Move to Bottom**.



To return only distinct options, select the **Distinct** menu option. This will toggle a set of checkboxes for each column in the source. Simply check any box next to the corresponding column to return distinct results only.


{{< warning >}}
When the target data table contains only a subset of the source data table, only select the check box next to the columns which **are** to be included in the target data table. Selecting all checkboxes could provide output that does not appear to be distinct.
{{< /warning >}}




To aggregate results, select the **Summarize** menu option. This will toggle a set of drop down boxes for each column in the target data table. The following summarization options are available:


* Group by (set as default)
* Sum
* Min
* Max
* First
* Last
* Count
* Mean
* Median
* Mode
* Std Dev
* Variance
* Product
* Absolute Val
* Quantile
* Skew
* Kurtosis
* Mean Abs Dev
* Cumulative Sum
* Cumulative Min
* Cumulative Max
* Cumulative Product

For more aggregation details, see the Analyze overview page [here](/docs/analyze/#aggregation).



### Data Filters


To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions)


for more details and examples.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.
{{< /caution >}}



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions)


for more details and examples.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.
{{< /caution >}}



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples






### Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop



### Lookup Operation


### Lookup Columns and Replacements


To view the columns available in the lookup table, simply select the **Inspect Source** button and one of its options to **Populate Lookup Source Mapping Table**. If desired, options are available to preview the data in the lookup table.



By default, the lookup table returns distinct values for all columns. Since a lookup returns the first matching value, it is not necessary to leave duplicate values in the lookup table. If desired, this option can be turned off by deselecting the **Distinct** checkbox for individual columns.



### Lookup Relationship Map


The **Lookup Relationship Map** is used to specify all columns used for matching. By using the **Guess** button, Analyze will populate the relationship map with all columns from the source data table which have a matching name in the lookup data table.



Additionally, these values can be entered manually by right-clicking the mouse button and selecting either **Insert Row** or **Append Row** to insert a row prior to the selected row or to insert a row at the bottom of the list, respectively. In a similar manner, items can be removed by right-clicking and selecting the **Delete** option.



### Field Value Map


The **Field Value Map** is used to append columns of data onto the target data table based upon matching values found. By default, using the **Guess** button will add all columns which were **not** used in the **Lookup Relationship Map** section. If not all columns are desired, items can be removed by right-clicking and selecting the **Delete** option.



Additionally, there are options available to rename the mapped columns simply by clicking into the **Update/Add Data Table Field** selection and adjusting the name as desired. Column order can also be adjusted as desired by right-clicking on an item and using the **Move to Top**, **Move Up**, **Move Down**, or **Move to Bottom** options.







## Examples


### Lookup Product Dimension Information


In this example, the modeler needs information from the product dimension table to make sense of the order fact table. As such, the *Import Order Fact* table is selected as the **Source Table**. The *Import Product Dim* table contains the desired lookup information, so it’s selected as the **Lookup Table Source**. Although available, no filters are applied to the lookup data table (nor any other data tables, for that matter).



In the **Table Data Selection** section, all columns are mapped from the source data table to the target data table. 



No **Data Filters** are applied to either source or target data. 



Lastly, the source data table is matched to the lookup data table using the *Product\_ID* field found in each table. Only the *Product\_Description* and *Unit\_Cost* columns are appended to the target data table, with *Unit\_Cost* being renamed to *Retail\_Unit\_Cost* in the process. 



In the resulting target data table, the *Product\_Description* and *Retail\_Unit\_Cost* columns have been added, based on matching values in the *Product\_ID* column. 
