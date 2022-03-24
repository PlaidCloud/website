---
title: Using Hierarchy Data
slug: hierarchies
description: Using and managing hierarchical data
date: 2022-01-25T07:39:48
---


PlaidCloud natively manages hierarchical data through our proprietary hierarchy storage system.  We decided to construct our own from scratch because
other solutions seem to present limitations that were not easily overcome.

The hierarchy storage supports not only hierarchical relationships but also properties, attributes, and values.  It is also designed to operate on large
structures and perform operations quickly including complex branch and leaf navigation.

## Main Hierarchy

Each dimension (i.e. hierarchical dataset) always consists of a `main` hierarchy.  Every member of the hierarchy is represented here.

Having a `main` hierarchy helps establish the complete set of leaf nodes in the set.


## Alternate or Attribute Hierarchies

Alternate hierarchies are different representations of the `main` hierarchy leaf nodes.  Alternate hierarchies can consist of a subset of both
leaf nodes and roll-up (i.e. folders) in the `main` hierarchy as well as its own set of unique roll-ups.

This provides for the maximum amount of flexibility by automatically updating alternate hierarchies when children of a roll-up change or to 
strictly control the alternate hierarchy members by specifying only the leaf nodes required.

{{< note >}}
Items in the `main` hierarchy have attribute labels showing alternate hierarchies for which they also belong
{{< /note >}}
