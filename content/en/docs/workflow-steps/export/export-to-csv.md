---
title: Export to CSV
slug: export-to-csv
description: Export an Analyze data table to PlaidCloud Document as a CSV delimited file
date: 2022-01-25T07:39:58
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


Export an Analyze data table to PlaidCloud Document as a CSV delimited file.



## Export Parameters


### Source and Target


See details here: [Source and Target](/docs/workflow-steps/common/table-data-selection)



### Data Format


The Export CSV transform is used to export data tables into delimited text files saved in PlaidCloud Document. This includes, but is not limited to, the following delimiter types:


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


The **Text Qualifier** section allows users to specify how to handle data with quotation marks and escape characters. Choose from the following settings:


* Special Characters (QUOTE_MINIMAL): Quote fields with special characters (anything that would confuse a parser configured with the same dialect and options). This is the default setting.
* All (QUOTE_ALL): Quote everything, regardless of type.
* Non-Numeric (QUOTE_NONNUMERIC): Quote all fields that are not integers or floats. When used with the reader, input fields that are not quoted are converted to floats.
* None (QUOTE_NONE): Do not quote anything on output. Quote characters are included in output with the escape character provided by the user. Note that only a single escape character can be provided.

Lastly, the **Use Windows Compatible Line Endings** checkbox is selected by default to ensure compatibility with Windows systems. It is advisable to leave this setting on unless working in a unix-only environment.



### Output File Type


All exported files are uncompressed, but the following compression options are available:


* Zip
* GZip
* BZip2


### Table Data Selection


The Table Data Selection tab is used to map columns from the source data table to the target data table. All source columns on the left side of the window are automatically mapped to the target data table depicted on the right side of the window. Using the **Inspect Source** menu button, there are a few additional ways to map columns from source to target:


* Populate Both Mapping Tables: Propagates all values from the source data table into the target data table. This is by default.
* Populate Source Mapping Table Only: Maps all values in the source data table only. This is helpful when modifying an existing workflow when source column structure has changed.
* Populate Target Mapping Table Only: Propagates all values into only the target data table.

In addition to each of these options, each choice offers the ability to preview the source data.


If the source and target column options aren’t enough, other columns can be added into the target data table in several different ways:


* **Propagate All** will insert all source columns into the target data table, whether they already existed or not.
* **Propagate Selected** will insert only selected source column(s).
* Right click on target side and select **Insert Row** to insert a row immediately above the currently selected row.
* Right click on target side and select **Append Row** to insert a row at the bottom (far right) of the target data table.

{{< warning >}}
Selecting **Propagate All** may effectively create a duplicate of every column. Analyze does not check to see if the columns are already mapped. Make sure duplicate column names do not exist.
{{< /warning >}}




To delete columns from the target data table, select the desired column(s), then right click and select **Delete**.



To rearrange columns in the target data table, select the desired column(s), then right click and select **Move to Top**, **Move Up**, **Move Down**, or **Move to Bottom**.



To return only distinct options, select the **Distinct** menu option. This will toggle a set of checkboxes for each column in the source. Simply check any box next to the corresponding column to return only distinct results.


{{< warning >}}
When the target data table contains only a subset of the source data table, select the check box next to only the columns which **are** to be included in the target data table. Selecting all checkboxes could provide output that does not appear to be distinct.
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


For more aggregation details, see the Analyze overview page [here](/docs/workflow-steps/common/aggregation).



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



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.


{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}




### Source Table Slicing (Limit)


See details here: [Source Table Slicing](/docs/workflow-steps/common/source-table-slicing-limit)



### Select Subset of Final Data


See details here: [Select Subset of Final Data](/docs/workflow-steps/common/select-subset-of-final-data)



### Final Data Table Slicing (Limit)


See details here: [Final Data Table Slicing](/docs/workflow-steps/common/final-data-table-slicing)







## Examples


No examples yet...
