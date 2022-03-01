---
title: Set Project Variable
slug: set-project-variable
description: Set a project variable for use during a workflow
date: 2022-01-25T07:40:18
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---

## Description


“Set Project Variable” sets project variables for use during the workflow. A variable name and value may contain any combination of valid characters, including spaces. Variables are referenced within the workflow by placing them inside curly braces. For example, *a\_variable* is referenced within a transform as *{a\_variable}* so it could be used in something like a formula or field value (e.g., {a\_variable} * 2).



## Variable List


The table will display the list of registered project variables and the current values. Enter the value for the variable desired. It’s also possible to set variable values without registering the variable first by simply adding the variable to the list.







## Examples


In this example, the *a\_variable* is set to a different value (*another\_value*).



In this example, a new unregistered variable (*unreg*) is created and set to *something new and different* by right-clicking on the table and selecting either *Insert* or *Append*.

