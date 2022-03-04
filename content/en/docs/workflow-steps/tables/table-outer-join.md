---
title: Table Outer Join
slug: table-outer-join
description: Combine data tables using specified join key(s)
date: 2022-01-25T07:39:49
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


Use, as you might have expected, to perform a **full** outer join operation on 2 data tables, combining them into a single data table based upon the join key(s) specified.


For more details on outer join methodology, see here: [Wikipedia SQL Full Outer Join](http://en.wikipedia.org/wiki/Join_%28SQL%29#Full_outer_join)



## Table A Data Selection


### Table Source


Specify the source data table by selecting it from the dropdown menu.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions)


for more details and examples.



### Duplicates


There is a checkbox option to use **Distinct Rows Only**. This is especially helpful in cases where duplicates may exist, but are not desired. As experienced modelers know, having non-distinct data in an SQL join can increase expected record count significantly.



Additionally, there is standard functionality to **Report Duplicates in Table** elsewhere. For more details on this capability, see details here:



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



### Source Columns and Replacements


Specify any columns to be included in the Outer Join here. Selecting the **Inspect Source** and **Populate Source Mapping Table** buttons will make these columns available for the join operation.



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



## Table B Data Selection


### Table Source


Specify the source data table by selecting it from the dropdown menu.



### Select Subset of Source Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions)


for more details and examples.



### Duplicates


There is a checkbox option to use **Distinct Rows Only**. This is especially helpful in cases where duplicates may exist, but are not desired. As experienced modelers know, having non-distinct data in an SQL join can increase expected record count significantly.



Additionally, there is standard functionality to **Report Duplicates in Table** elsewhere.



### Duplicates


To report duplicates, select the **Report Duplicates in Table** checkbox and then specify an output table which will contain all of the duplicate records.




{{< caution >}}
This will **not** remove the duplicate items from the target data table. To remove duplicate items, use the **Distinct** menu options as specified in the [Table Data Selection](../transforms/common_features#table-data-selection) section.
{{< /caution >}}



### Source Columns and Replacements


Specify any columns to be included in the Outer Join here. Selecting the **Inspect Source** and **Populate Source Mapping Table** buttons will make these columns available for the join operation.



### Source Table Slicing (Limit)


To limit the data, check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is **not** included in count)
* **End at Row:** Last row of data to include. Note that this is different from simply counting rows at the end to drop



## Table Output


### Target Table


Specify the **Target Table** name by either selecting an existing data table from the dropdown menu or typing a new data table name into the same menu. By default, the **Target Table** is automatically populated with the specific transform’s name. Note that data tables must follow Linux naming conventions. As such, we recommend that names only consist of alphanumeric characters. Analyze will automatically scrub any invalid characters from the name.



### Join Map


Specify join conditions. Using the **Guess** button will find all matching columns from both **Table A** and **Table B**. To add additional columns manually, right click anywhere in the section and select either **Insert Row** or **Append Row**, to add a row prior to the currently selected row or to add a row at the end, respectively. Then, type the column names to match from **Table A** to **Table B**. To remove a field from the **Join Map**, simply right-click and select **Delete**.



### Target Output Columns


Specify the columns to appear in the target data table. Selecting the **Propagate** button will insert all columns listed in the **Source Columns and Replacements** section of both **Table A** and **Table B**. Any columns included in the **Join Map** will only be listed a single time.



To add additional columns manually, right click anywhere in the section and select either **Insert Row** or **Append Row**, to add a row prior to the currently selected row or to add a row at the end, respectively. Then, type the column name. To remove a field, simply right-click and select **Delete**.



### Select Subset of Final Data


Any valid Python expression is acceptable to subset the data. Please see [Expressions](/docs/expressions) for more details and examples



### Final Data Table Slicing (Limit)


To limit the data, simply check the **Apply Row Slicer** box and then specify the following:


* **Initial Rows to Skip:** Rows of data to skip (column header row is not included in count)
* **End at Row:** Last row of data to include. This is different from simply counting rows at the end to drop



## Examples


### Join Automobile Manufacturers with Models


In this example, consider the following source data tables. First is a list of automobile manufacturers.




| Mfg_ID | Manufacturer |
| 1 | Aston Martin |
| 2 | Porsche |
| 3 | Lamborghini |
| 4 | Ferrari |
| 5 | Koenigsegg |

Next is a list of automobile models with a manufacturer ID. Note that there are several models with no manufacturer.




| ModelName | Mfg_ID |
| Aventador | 3 |
| Countach | 3 |
| DBS | 1 |
| Enzo | 4 |
| One-77 | 1 |
| Optimus Prime |  |
| Batmobile |  |
| Agera | 5 |
| Lightning McQueen |  |

To get a list of models by manufacturer, it makes sense to join on *Mfg_ID*. By leveraging outer join concepts, the output will also be able to show those items which do not have any matches.



First, specify parameters for **Table A Data Selection**. The source data table is selected and all columns are listed.



Next, specify parameters for **Table B Data Selection.** Once again, the source data table is selected and all columns are listed.



Finally, the join conditions are set in the **Table Output** tab. Using the **Guess** button, Analyze properly identifies the *Mfg_ID* column to use as the **Join Key**. Lastly, the 


**Target Output Columns** are specified automatically using the **Propagate** button. This effectively includes all columns from all tables, with any join columns obviously only being included a single time. Note that the columns are sorted alphabetically, first by *Manufacturer* and next by *ModelName*.



As expected, the final output includes all rows from both tables, whether they had a match in both tables or not. As such, this time *Porsche* does indeed show up despite having no models. Additionally, *Batmobile*, *Lightning McQueen*, and *Optimus Prime* are included in the results even though none of them have a manufacturer. Besides, who can say ‘No’ to them?
