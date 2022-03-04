---
title: File Import File Selection
---

### Import File Selector

The file selector in this transform allows you to choose a file stored in a PlaidCloud Document location for import.

You can also choose a directory to import and all files within that directory will be imported as part of the transform run.

{{< caution >}}
When choosing a directory to import, ensure all files have the same format
{{< /caution >}}

#### Selecting a Document Account

Choose a PlaidCloud Document account for which you have access.  This will provide you with the ability to select a directory or file in the next selection.

#### Search Option

The **Search** option allows for finding all matching files below a specified directory path to import.  This can be particularly useful if many files need to be
included but they are stored in nested directories or are mixed in with other files within the same directory which you do not want to import.

{{< note >}}
Using a common naming convention for files of similar type and purpose makes it easier to use a single import step
{{< /note >}}

The search path selected is the starting directory to search under.  The search process will look for all files within that directory as well as sub-directories that
match the search conditions specified.  Ensure the search criteria can be applied to the files within the sub-directories too.

The search can be applied using the following conditions:
 * **Exact**: Match the search text exactly
 * **Starts With**: Match any file that starts with the search text
 * **Contains**: Match any file that contains the search text
 * **Ends With**: Match any file that ends with the search text

#### File or Directory Selection Option

When a specific file or directory of files are required for import, picking the file or directory is a better option than using search.

To select the file or directory, simply use the browse button to pick the path for the Document account selected above.

#### Variable Substition

For both the search option and specific file/directory option, variables can be used with in the path, search text, and file names.

An example that uses the `current_month` variable to dynamically point to the correct file:

```
legal_entity/inputs/{current_month}/ledger_values.csv
```