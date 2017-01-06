---
layout: post
title: Data Exploration | PivotClient | ASP.NET | Syncfusion
description: data exploration
platform: aspnet
control: PivotClient
documentation: ug
---

# Data Exploration

## Searching

### Searching by Member

By clicking the Split Button of a field, Member Editor dialog opens through which members are searched and get displayed from the members list inside the Member Editor dialog.

![](Data-Exploration_images/relationalsearchgrouping.png) 

## Filtering

### Filtering by Member

By clicking the  Split Button of a field, Member Editor dialog opens through which members are filtered by checking and unchecking the check boxes corresponding to the members. 

![](Data-Exploration_images/relationalfilterbymember.png)

 On clicking the "OK" button, based on the selected members in the Member Editor dialog, PivotReport gets updated and refreshes the PivotGrid and PivotChart controls.  The "Cancel" button is used to cancel the selection. 

![](Data-Exploration_images/relational-filter-grouping.png)

The above filter illustrates that the members 'Canada' and 'Germany' are alone included in the Grid and Chart controls.

## Grouping

The data can be grouped when more than one field element is added to Categorical or Series in Axis Element Builder.  Based on the order of addition, data is grouped and the report is updated. In the following example, the **Date** dimension values get grouped, with respect to **Country** dimension values.  Likewise multiple field members can be grouped by dragging the elements from pivot field list to Axis Element Builder.

![](Data-Exploration_images/relational-grouping.png)
