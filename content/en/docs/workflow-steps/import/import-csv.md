---
title: Import CSV
slug: import-csv
description: Import delimited text files from PlaidCloud Document
date: 2022-01-25T07:39:55
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


Import delimited text files from PlaidCloud Document. This includes, but is not limited to, the following delimiter types:


* comma
* pipe
* semicolon
* tab
* space
* other/custom (tilde, dash, etc)

## Import Parameters


### Source and Target


To establish the source and target, first select the data table to be exported from the **Source Table** dropdown menu. Next, select the target file path from PlaidCloud Document using the dropdown menu to select the appropriate account before navigating to the actual directory in the section immediately below. Finally, provide the target file with a descriptive name.

{{< note >}}
Providing a file extension is advised, but not required by Analyze. The data table will be exported into the appropriate file format with or without an extension.
{{< /note >}}




### Inspect Selected Source File


Analyze provides built-in functionality to preview source file data so users are not required to find the original file and open to recall its contents. Simply select **Inspect Source File** and a new window will open with a data preview (file stats are also available in a separate tab). Since some files can be quite large, the default limit is set to preview only 300 rows, but this can be adjusted as necessary.



Inspecting the source file will also give Analyze a chance to determine the delimiter being used.



### Data Format


As mentioned above, **Inspect Source File** will attempt to determine the delimiter in the source file. If another delimiter is desired, use this section to specify the delimiter. Users can choose from a list of standard delimiters or specify a different value as needed.


* Excel CSV (comma separated)
* Excel TSV (tab separated)
* User Defined Separator –>


	+ comma (,)
	+ pipe (|)
	+ semicolon (;)
	+ tab
	+ space ( )
	+ other/custom (tilde, dash, etc)

To specify a custom delimiter, select **User Defined Separator –>** and then **Other –>**, and type the custom delimiter into the text box.



The **Text Qualifier** section allows users to specify how to handle the data with regards to quotation marks and escape characters. Choose from the following settings:


* Special Characters (QUOTE_MINIMAL): Quote fields with special characters (anything that would confuse a parser configured with the same dialect and options). This is the default setting.
* All (QUOTE_ALL): Quote everything, regardless of type.
* Non-Numeric (QUOTE_NONNUMERIC): Quote all fields that are not integers or floats. When used with the reader, input fields that are not quoted are converted to floats.
* None (QUOTE_NONE): Do not quote anything on output. Quote characters are included in output with the escape character provided by the user. Note that only a single escape character can be provided.



### Row Skipping

For input files with extraneous records, you can specify any number of rows to ignore from the top and/or bottom of the input file. This is especially helpful for files with control sums at the bottom.

### Column Headers


### Data Quality

Choose from any of the following options:

* Skip Quality Check: Analyze inspects each input file to ensure that each row of data contains the same number of columns. It also checks to make sure that quotation marks are not unbalanced, which could create data errors upon loading the file.
* Error on Bad Data Lines: If any rows have too few or too many columns, an error will be raised and the target data table will not be created. By default, this is turned off and bad lines are simply dropped from the target data table.
* Skip Space After Delimiter: Ignore a single space after the delimiter. This is enabled by default.


{{< note >}}
Selecting the **Skip Quality Check** box reduces overhead by removing an additional pass to each import step. While the quality check is helpful in determining the quality of source files, it can impact performance for larger files. Turn this setting **ON** to skip the check for large files that have structural integrity.
{{< /note >}}



### Parsing Overrides

Analyze handles boolean and null values specially. This section provides the ability to specify values which should be treated specially.


* Values Considered TRUE: Any values which should be converted to boolean TRUE value should be entered here. Use a comma delimiter to specify multiple values. For example, adding **YES** would convert all instances of **YES** to **TRUE**.
* Values Considered FALSE: Any values which should be converted to boolean FALSE value should be entered here. Use a comma delimiter to specify multiple values. For example, adding **NO** would convert all instances of **NO** to **FALSE**.
* Enable NA Conversion: Any values which should be converted to **NULL** values should be entered here. Use a comma delimiter to specify multiple values. For example, adding the failed Microsoft Excel vlookup value of **#N/A** would convert all instances of **#N/A** to **NULL**.


### Data Filters

To allow for maximum flexibility, data filters are available on the source data and the target data. For larger data sets, it can be especially beneficial to filter out rows on the source so the remaining operations are performed on a smaller data set.


### Select Subset of Source Data

Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.


### Duplicates

To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.

{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



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

Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples.


### Final Data Table Slicing (Limit)

To limit the data, simply check the **Apply Row Slicer** box and then specify the following:

* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop


### Text Replacement

To perform basic Find/Replace operations, right click and select **Insert Row** or **Append Row** to add a new row prior to your selection or at the end of the list, respectively. 
Then, fill out the **Find** and **Replace With** fields. This will replace all instances found in the target data table, regardless of column position. Keep in mind that text 
replacement is case sensitive, so searching for *analyze* is not the same as searching for *Analyze*.


{{< note >}}
Replacement text should **not** have quotation marks unless you want the replaced text to contain those quotation marks
{{< /note >}}


## Examples

No examples yet...

---

## Common Component Usage

{{< include "common-import-file-selection" >}}

{{< include "common-import-target-selection" >}}

{{< include "common-data-mapper" >}}

{{< include "common-data-filter" >}}
