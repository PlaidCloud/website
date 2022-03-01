---
title: Rename Workflow
slug: rename-workflow
description: Rename an Existing PlaidCloud Analyze Workflow
date: 2022-01-25T07:39:51
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---


## Description


Rename an existing PlaidCloud Analyze workflow.

{{< note >}}
If the renamed workflow already exists, an error will be written to the log noting that *Workflow {workflow} in project {project} already exists.* No action will be taken. This effectively limits the **Rename Workflow** transform to a single use.
{{< /note >}}


## Workflow to Rename


First, select the Project which contains the workflow to be renamed from the **Project** dropdown menu.



Next, select the particular workflow to be renamed from the **Workflow** dropdown menu.



Finally, enter the new workflow name in the **Rename To** field. Remember that the name should be unique to the Project.








## Examples


In this example, the workflow *Blank Workflow Copied by Analyze* is renamed to *Blank Workflow Renamed by Analyze*. Additionally, the default value of **ERROR if the target workflow already exists** ensures that nothing happens should the specified workflow already exist. 


