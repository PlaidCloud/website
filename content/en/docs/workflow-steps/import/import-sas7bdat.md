---
title: Import SAS7BDAT
slug: import-sas7bdat
description: Import SAS table files from PlaidCloud Document
date: 2022-01-25T07:39:57
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---




| Parameter | Value |
| **Category** | Import |
| **Operation** | import\_sas7bdat |
| **Workflow Icon** | Icon |
| **Input Type** | PlaidCloud Document File |
| **Output Type** | PlaidCloud Analyze Table |

# Description


Import SAS table files from PlaidCloud Document.



# Import Parameters


## Source and Target


To establish the source and target, first select the data table to be exported from the **Source Table** dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.



***Note***


Providing a file extension is advised, but not required by Analyze. The data table will be exported into the appropriate file format with or without an extension.



## File Encoding Conversion


See details here: [File Encoding Conversion](https://plaidcloud.com/docs/plaidcloud/workflows/transforms/common_features#file-encoding-conversion)



## Table Data Selection


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

*Warning*


Selecting **Propagate All** may effectively create a duplicate of every column. Analyze does not check to see if the columns are already mapped. Make sure duplicate column names do not exist.



To delete columns from the target data table, select the desired column(s), then right click and select **Delete**.



To rearrange columns in the target data table, select the desired column(s), then right click and select **Move to Top**, **Move Up**, **Move Down**, or **Move to Bottom**.



To return only distinct options, select the **Distinct** menu option. This will toggle a set of checkboxes for each column in the source. Simply check any box next to the corresponding column to return distinct results only.



*Warning*


When the target data table contains only a subset of the source data table, only select the check box next to the columns which **are** to be included in the target data table. Selecting all checkboxes could provide output that does not appear to be distinct.



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

*Todo*


For more aggregation details, see the Analyze overview page [here](/docs/analyze/#aggregation).



## Data Filters


To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.



## Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



***Note***


Compound filters **must** have individual elements wrapped in parentheses. For example, if filtering for Temperature and Humidity, a valid filter would look like this:



## Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.



*Caution*


This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.



## Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.


Example code here



## Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



***Note***


Compound filters **must** have individual elements wrapped in parentheses. For example, if filtering for Temperature and Humidity, a valid filter would look like this:



## Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.



*Caution*


This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.



## Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop


## Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.


Example code here



## Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop


# Workflow Configuration Forms



# Examples


## Import SAS Table


In this example, the SAS table *sas7bdat.sas7bdat* is imported from the *Analyze Demo Input* directory of PlaidCloud Document. The Analyze Target Table is *Import SAS Table*. 



All columns are mapped from source to target as *Float* or *String* data types, for number data and string data, respectively. 



No **Data Filters** are used.

