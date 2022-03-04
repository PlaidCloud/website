---
title: Import Excel
slug: import-excel
description: Import worksheets from Excel files within PlaidCloud Document
date: 2022-01-25T07:39:55
---

## Description

Import specific worksheets from Microsoft Excel files from PlaidCloud Document. Analyze supports the legacy Excel format (XP/2003) as well as the new format (2007/2010/2013). This includes, but is not limited to, the following file types:

* XLS
* XLSX
* XLSB
* XLSM

## Examples

{{< include "no-examples" >}}

---

## Unique Configuration Items

### Remove non-ASCII Characters

By selecting this option, the import will remove any content that is not ASCII.  While PlaidCloud fully supports Unicode (UTF-8), real-world
Excel files can contain all sorts of encodings and stray characters that make them challenging to process.

If the content of the Excel file is expected to be ASCII only, checking this box will help ensure the import process runs smoothly.

{{< caution >}}
If your data contains text from locations throughout the world it may contain non-ASCII names and phrases
{{< /caution >}}


### Delete Files After Import

This option will allow the import process to delete the file from the PlaidCloud Document account after a successful import has completed.

This can be useful if the import files are generated can be recreated from a system of record or there is no reason to retain the raw input files
once they have been processed.


### Header

Since Excel files may or may not contain headers, PlaidCloud provides a way to either use the headers, ignore headers, or use column order to determine the column alignment.
* **No Header**: The file contains no header.  Use the source list in the *Data Mapper* to determine the column alignment
* **Has Header - Use Header and Override Field List**: The file has a header.  Use the header names specified and ignore the source list in the *Data Mapper*.
* **Has Header - Skip Header and Use Field List Instead**: The file has a header but it should be ignored.  Use the header names specified by the source list in the *Data Mapper*.

### Row Selection

For input files with extraneous records, you can specify a number of rows to skip before processing the data.  This is useful if files contain header blocks that must be skipped before arriving at the tabular data.

### Worksheets to Import

Because workbooks may contain many worksheets with different data, it is possible to select which worksheets should be imported in the current import process.  The options are:

* All Worksheets
* Worksheets Matching Search
* Selected Worksheets

#### Using Worksheet Search

The search functionality for worksheets allows inclusion of worksheets matching the search criteria.  The search criteria allows for:
* **Starts With**: The worksheet name starts with the search text
* **Contains**: The worksheet name contains the search text
* **Ends With**: The worksheet name ends with the search text

#### Find Sheets in Selected File

The find sheets button will open the Excel file and list the worksheets available in the table.  Mark the checkboxes in the table for the worksheets to be included in the import.

{{< note >}}
When populating the *Data Mapper*, the first worksheet found in the list will be used.  Ensure all worksheets have a similar format that are included in the import step.
{{< /note >}}

---

## Common Configuration Items

{{< include "common-import-file-selection" >}}

{{< include "common-import-target-selection" >}}

{{< include "common-data-mapper" >}}

{{< include "common-data-filter" >}}