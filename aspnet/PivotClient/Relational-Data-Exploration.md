---
layout: post
title: Data Exploration | PivotClient | ASP.NET | Syncfusion
description: data exploration
platform: aspnet
control: PivotClient
documentation: ug
---

# Data exploration

## Filtering

### Filtering by member

By clicking the split button of a field, the member editor dialog opens through which members are filtered by checking and unchecking the check boxes corresponding to the members.

![Member editor filtering in ASP NET pivot client control](Data-Exploration_images/relationalfilterbymember.png)

 By clicking OK, the pivot report gets updated and the pivot grid and pivot chart controls get refreshed based on selected members in the member editor dialog. The Cancel button is used to cancel the selection.

![Filtered data in ASP NET pivot client control](Data-Exploration_images/relational-filter-grouping.png)

The above filter illustrates that the members 'Canada' and 'Germany' are alone included in the grid and chart controls.

## Grouping

The data can be grouped when more than one field element is added to categorical or series in the axis element builder. Based on the order of addition, the data is grouped and the report is updated. In the following example, the **Date** dimension values can be grouped with respect to **Country** dimension values. Likewise, multiple field members can be grouped by dragging the elements from the pivot field list to the axis element builder.

![Grouping in ASP NET pivot client control](Data-Exploration_images/relational-grouping.png)

## Searching

Members can be searched and displayed from the members list in the member editor dialog.

![Member editor searching in ASP NET pivot client control](Data-Exploration_images/relationalsearchgrouping.png)
