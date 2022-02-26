---
title: Run Workflow
slug: run-workflow
description: Run an existing workflow
date: 2022-01-25T07:40:18
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---




| Parameter | Value |
| **Category** | workflow |
| **Operation** | workflow\_run |
| **Workflow Icon** | Icon |
| **Input Type** |  |
| **Output Type** |  |

# Description


“Run Workflow” runs an existing workflow.



# Workflow to Run


First, select the Project which contains the workflow to be run from the **Project** dropdown menu.



Next, select the particular workflow to be run from the **Workflow** dropdown menu.



Additionally, there is an option to **Wait until processing completes before continuing.** Selecting this checkbox will defer execution of the current workflow until the called workflow is completed with its execution. By default, this option is disabled, meaning that the current workflow in which this transform resides will continue processing in parallel along with the called workflow.



# Workflow Configuration Forms



# Examples


## Await Further Processing Until Other Workflow Completes


In this example, the *Blank Workflow Created by Analyze* workflow is run from the *Default* project. Note that the **Wait until processing completes before continuing** option is selected. As such, this step will take however long it takes to run the *Blank Workflow Created by Analyze* workflow. No further steps in this transform’s workflow will be executed until the *Blank workflow Created by Analyze* workflow has completed running.



## Continue Processing in Parallel to Other Workflow’s Execution


In this example, the *Blank Workflow Copied by Analyze* workflow is run from the *Default* project. Since the **Wait until processing completes before continuing** option is not selected, the workflow from which this step was launched will continue running. Both workflows will run in parallel, potentially creating resource issues if there are dependencies between the two workflows.

