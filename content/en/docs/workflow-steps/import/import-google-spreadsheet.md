---
title: Import Google Spreadsheet
slug: import-google-spreadsheet
description: Import specific worksheets from Google Spreadsheet files
date: 2022-01-25T07:39:58
---


## Description

Import specific worksheets from Google Spreadsheet files.


## Examples

No examples yet...

---

## Unique Configuration Items

### Source Spreadsheet Selection

Accessing Google Spreadsheet data requires a valid Google user account. This requires set up in Tools. For details on setting up a Google account connection, see here: [PlaidCloud Tools – Connection](/docs/tools/data-connections).

Once all necessary accounts have been set up, select the appropriate **Google Account** from the drop down list.

Next, specify the **Spreadsheet** to import from the dropdown menu containing all available files associated with the specified **Google Account**.

{{< note >}}
Make sure the provided user account has access to the specified file, especially if the file is owned by another user.
{{< /note >}}


### Column Headers

{{< note >}}
Due to technical limitations, all columns from Google Spreadsheets are imported as String data type. Boolean, Numerical and/or Date/Time data types must be explicitly specified in the mapper.
{{< /note >}}


---

## Common Configuration Items

{{< include "common-remove-non-ascii" >}}

{{< include "common-delete-files-after-import" >}}

{{< include "common-import-target-selection" >}}

{{< include "common-data-mapper" >}}

{{< include "common-data-filter" >}}
