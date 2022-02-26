---
title: Import Excel
slug: import-excel
description: Import worksheets from Excel files within PlaidCloud Document
date: 2022-01-25T07:39:55
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---




| Parameter | Value |
| **Category** | Import |
| **Operation** | import\_excel |
| **Workflow Icon** | Icon |
| **Input Type** | PlaidCloud Document File |
| **Output Type** | PlaidCloud Analyze Table |

# Description


Import specific worksheets from Microsoft Excel files from PlaidCloud Document. Analyze supports the legacy Excel format (XP/2003) as well as the new format (2007/2010/2013). This includes, but is not limited to, the following file types:


* XLS
* XLSX
* XLSB
* XLSM

# Import Parameters


## Source and Target


To establish the source and target, first select the data table to be exported from the **Source Table** dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.



***Note***


Providing a file extension is advised, but not required by Analyze. The data table will be exported into the appropriate file format with or without an extension.



## Worksheets to Import


*Todo*


worksheets to import



## Columns to Import


Specify the columns to import into the target data table. A single value like *B* means to import only column B. Specify consecutive column ranges with a colon (:) delimiter, such as *A:H* to import the first 8 columns. Use a comma (,) delimiter to specify non-consecutive columns such as “A,C,E,G” to import every other column. Additionally, mixed delimiters are allowed. An entry such as *A,C:E* will import columns A, C, D, and E only.



***Note***


If uncertain, leave this section blank and use [Table Data Selection](https://plaidcloud.com/docs/plaidcloud/workflows/transforms/common_features#table-data-selection) to select the target data table columns to include.



## Other NA Values


Convert values to **Null**. By default, **NA** is included. If there are additional values, specify them with a comma (,) delimiting each item.



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



To return only distinct options, select the **Distinct** menu option. This will toggle a set of checkboxes for each column in the source. Simply check any box next to the corresponding column to return only distinct results.



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


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions)


for more details and examples.



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



***Note***


It is advisable to not use the **Select Subset of Source Data** feature when importing multiple worksheets because the filter is only applied to the first worksheet. Subsequent worksheets will be imported with no regard to the subsetting expression.



## Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.



*Caution*


This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common\_features#table-data-selection) section.



***Note***


It is advisable to not use the **Duplicates** feature when importing multiple worksheets because the duplicates are only checked on the first worksheet. Subsequent worksheets will be imported with no regard to the existence of duplicates.



## Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop


***Note***


It is advisable to not use the **Source Table Slicing (Limit)** feature when importing multiple worksheets because the slice is only applied to the first worksheet. Subsequent worksheets will be imported with no regard to the slicing limits.



## Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.


Example code here



## Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop


# Workflow Configuration Forms



# Examples


## Import Excel 2007 File


In this example, a file with the *.xlsx* file extension is imported. First, the file, *Export XLS 2007 format.xlsx*, is selected from the appropriate Document directory, *Analyze Demo Output*. In this instance, *Sheet1* is the only worksheet available, so it is selected from the **Selected Worksheets** section. The **Columns to Import** option is used to specify a subset of columns. By using the subset, *A,C:D*, only columns A, C, and D are included. No **Other NA Values** are given.



Next, all available columns are mapped in the **Table Data Selection**. Keep in mind that since the **Columns to Import** option was used in the **Import Parameters** tab, only 3 columns are available here. No additional operations are performed.



## Import Zipped Excel Legacy File


In this example, a file with the *.xls* file extension is imported. First, the file, *Export XLS Legacy format and zipped.xls.zip*, is selected from the appropriate Document directory, *Analyze Demo Output*. Notice that Analyze will automatically unzip this file if needed. No parameters are required to specify that the file needs to be unzipped. In this instance, *Sheet1* is the only worksheet available, so it is selected from the **Selected Worksheets** section. The **Columns to Import** option is not used, nor is the **Other NA Values** option.



Next, all available columns are mapped in the **Table Data Selection**. No additional operations are performed.



## Import Multiple Worksheets From the Same File


In this example, a collection of stock prices is imported from an Excel workbook, *PlaidCloud Analyze Demo – Import All Stock.xlsx*, from the appropriate Document directory, *Analyze Demo Input*. Once the workbook is selected from the dropdown menu, the Analyze **Target Table** name is set to *Import Excel All at Once*. Next, the **All Worksheets** button was used to import all available worksheets.



Next, all available columns are mapped in the **Table Data Selection**. No additional operations are performed.



## BCS Demo – Import Computer Rankings


For an example showing how to import Microsoft Excel data, please see the [Import Excel](https://plaidcloud.com/docs/plaidcloud/analyze/models/demo_2013_bcs_rankings#import-excel) section of the BCS Demo.

