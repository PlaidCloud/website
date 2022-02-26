---
title: Import JSON
slug: import-json
description: Import JSON text files from PlaidCloud Document
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
| **Operation** | import\_json |
| **Workflow Icon** | Icon |
| **Input Type** | PlaidCloud Document File |
| **Output Type** | PlaidCloud Analyze Table |

# Description


Import JSON text files from PlaidCloud Document.



For more details on JSON files, see the JSON official website here: <http://json.org/>.



JSON files do *not* retain column order. The column order in the source file does not necessarily reflect the column order in the imported data table.



# Import Parameters


## Source and Target


To establish the source and target, first select the data table to be exported from the **Source Table** dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.



***Note***


Providing a file extension is advised but not required by Analyze. The data table will be exported into the appropriate file format with or without an extension.



## JSON Data Orientation


Consider the following data set:




| ID | Name | Gender | State |
| 1 | Jack | M | MO |
| 2 | Jill | F | MO |
| 3 | George | M | VA |
| 4 | Abe | M | KY |

JSON files can be imported from one of three data formats:


* Records: Data is stored in Python dictionary sets, with each row stored in {Column -> Value, …} format. For example:


```
[{ "ID": 1, "Name": "Jack", "Gender": "M", "State": "MO" }, { "ID": 2, "Name": "Jill", "Gender": "F", "State": "MO" }, { "ID": 3, "Name": "George", "Gender": "M", "State": "VA" }, { "ID": 4, "Name": "Abe", "Gender": "M", "State": "KY" }]
```

* Index: Data is stored in nested Python dictionary sets, with each row stored in {Index -> {Column -> Value, …},…} format. For example:


```
{ "0": { "ID": 1, "Name": "Jack", "Gender": "M", "State": "MO" }, "1": { "ID": 2, "Name": "Jill", "Gender": "F", "State": "MO" }, "2": { "ID": 3, "Name": "George", "Gender": "M", "State": "VA" }, "3": { "ID": 4, "Name": "Abe", "Gender": "M", "State": "KY" } }
```

* Split: Data is stored in a single Python dictionary set, values stored in lists. For example:


```
{ "columns": ["ID", "Name", "Gender", "State"], "index": [0, 1, 2, 3], "data": [ [1, "Jack", "M", "MO"], [2, "Jill", "F", "MO"], [3, "George", "M", "VA"], [4, "Abe", "M", "KY"] ] }
```


## File Encoding Conversion


*Todo*


file\_encoding\_conversion



## Table Data Selection


Remember that JSON files do *not* retain column order. Adjustments to column order may be required during this step.



## Data Filters


To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.



## Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



*Note*


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


## Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expression](https://plaidcloud.com/docs/plaidcloud/workflows/index#expressions) for more details and examples.



***Note***


Compound filters **must** have individual elements wrapped in parentheses. For example, if filtering for Temperature and Humidity, a valid filter would look like this:



## Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop


# Workflow Configuration Forms



# Examples


## Import Record-Oriented JSON Data


In this example, the JSON data is stored in the record-oriented format. The first record is highlighted within the red box below. Note that each **Column -> Value** pair is comma-delimited and that the entire record is enclosed within curly braces ({ }) because it is a Python dictionary set.



Note that the **JSON Data Orientation** is listed as *Records* to reflect the structure accordingly.



Finally, the target columns are specified in the **Table Data Selection** tab. As previously mentioned, note that the target data table did not retain the column order listed in the original file. If desired, the columns can be rearranged as necessary.

