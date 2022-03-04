---
title: Import Google Spreadsheet
slug: import-google-spreadsheet
description: Import specific worksheets from Google Spreadsheet files
date: 2022-01-25T07:39:58
---


## Description


Import specific worksheets from Google Spreadsheet files.



### Source and Target


Accessing Google Spreadsheet data requires a valid Google user account. This requires set up in Tools. For details on setting up a Google account connection, see here: [PlaidCloud Tools – Connection](/docs/tools/data-connections).



Once all necessary accounts have been set up, select the appropriate **Google Account** from the drop down list.



Next, specify the **Spreadsheet** to import from the dropdown menu containing all available files associated with the specified **Google Account**.



Finally, be sure to provide a valid **Target Table** name for the data set. For target naming conventions, see details here:


{{< note >}}
Make sure the provided user account has access to the specified file, especially if the file is owned by another user.
{{< /note >}}



### Column Headers

{{< note >}}
Due to technical limitations, all columns from Google Spreadsheets are imported as String data type. Boolean, Numerical and/or Date/Time data types must be explicitly specified in the mapper.
{{< /note >}}




### Data Filters


To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.



{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.






### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.


{{< note >}}
Use of the **Select Subset of Source Data** feature is not recommended when importing multiple spreadsheets because the filter is only applied to the first spreadsheet. Subsequent spreadsheets will be imported with no regard to the subsetting expression.
{{< /note >}}




### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.



{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}


{{< note >}}
Use of the the **Duplicates** feature is not recommended when importing multiple spreadsheets because the duplicates are only checked on the first spreadsheet. Subsequent spreadsheets will be imported with no regard to the existence of duplicates.
{{< /note >}}




### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop

{{< note >}}
Use of the **Source Table Slicing (Limit)** feature is not recommended when importing multiple spreadsheets because the slice is only applied to the first spreadsheet. Subsequent spreadsheets will be imported with no regard to the slicing limits.
{{< /note >}}




### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.






### Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop






## Examples

No examples yet...