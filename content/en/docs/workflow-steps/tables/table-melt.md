---
title: Table Melt
slug: table-melt
description: Flip columns to rows
date: 2022-01-25T07:39:49
---


## Description


Use to convert short, wide data tables into long, narrow data tables. Select columns are transposed, with the column names converted into values across multiple rows.


Perhaps the easiest example to understand is to think of a data table with months listed as column headers:




| Budget Category | Jan | Feb | Mar | Apr | May | June |
| Electric
Costs | 54 | 56 | 72 | 65 | 81 | 84 |

Melting this data table would convert all of the month columns into rows.




| Budget Category | Month | Cost |
| Electricity Costs | JAN | 54 |
| Electricity Costs | FEB | 56 |
| Electricity Costs | MAR | 72 |
| Electricity Costs | APR | 65 |
| Electricity Costs | MAY | 81 |
| Electricity Costs | JUN | 84 |

By specifying which columns to transpose and which columns to leave alone, this becomes a powerful tool. Making this conversion in other ETL tools could require a dozen more steps.



## Source and Target Parameters


### Source and Target


To establish the source and target, first select the data table to be exported from the **Source Table** dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.

{{< note >}}
Providing a file extension is advised but not required by Analyze. The data table will be exported into the appropriate file format with or without an extension.
{{< /note >}}




## Pre-Melt Table Data Selection


This section is a bit different from the standard Table Data Selection. Basically this is used to specify which columns are to be used in the Melt operation. This includes ID columns and Variable/Value columns.


{{< note >}}
The column layout in the Pre-Melt Table Data Selection does **NOT** reflect the column layout of the output data table. Target data table layout is specified in the Melt Layout section.
{{< /note >}}




For more details regarding Table Data Selection, see details here: [Table Data Selection](/docs/workflow-steps/common/table-data-selection)



## Data Filters


To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions)


for more details and examples.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions)


for more details and examples.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples



### Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop



## Melt Layout


There is a **Guess Layout** button available to allow Analyze a first crack at specifying ID columns. By default, all text (data type of **String**) columns are placed in the **Keys** section. Numeric columns are not placed into **Keys** by default, but they are allowed to be there based on the model’s needs.


{{< note >}}
The target data table’s structure will consist of all **ID Columns** plus the names specified for **Variable Column Name** and **Value Column Name**.
{{< /note >}}




### Columns to Use as IDs (Keys)


ID columns are the columns which remain in tact. These columns are effectively repeated for every instance of a variable/value combination. For a monthly table, this would result in 12 repetitions of ID columns.



ID columns can be added automatically or manually. To add the columns automatically, use the aforementioned **Guess Layout** button. To add additional columns manually, right click anywhere in the section and select either **Insert Row** or **Append Row**, to add a row prior to the currently selected row or to add a row at the end, respectively. Then, type the column name to use as an ID.



To remove a field from the **IDs**, simply right-click and select **Delete**.



### Melt Result Column Naming


There are 2 values to specify. Both of these values will become column names in the target data table.


* **Variable Column Name:** As specified in the transform, *The variable names are derived from the current source column names*. Essentially, specify a column name which will represent the data originally represented in the source data table columns.
* **Value Column Name:** Specify a column name to represent the data represented within the source data table. Typically this will be a numerical unit: Dollars, Pounds, Degrees, Percent, etc.





## Examples


No examples yet...
