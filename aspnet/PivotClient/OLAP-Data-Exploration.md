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

After clicking split button of a dimension, the Member Editor dialog opens through which members are filtered by checking and unchecking the check boxes corresponding to the members. By clicking OK, the OLAP report gets updated and the pivot grid and pivot chart controls get refreshed based on the selected members in the member editor dialog. The Cancel button is used to cancel the selection.

![Member editor filtering in ASP NET pivot client control](Data-Exploration_images/filtering.png)

The above filter illustrates the members France and Germany, along with New South Wales and Queensland are excluded from the grid and chart controls.

### Filtering by value

I> This feature is applicable only for the OLAP data source bound from the server-side.

The filtering tab in the sorting and filtering dialog of pivot client provides the options to apply custom filters on the multi-dimensional data. It enables you to filter the rows and columns of the selected measure.

* **Column filter**: Filters the columns related to the specified measure according to the condition applied for filtering.
* **Row Filter**: Filters the columns related to the specified measure according to the condition applied for filtering.

The Sorting And Filtering dialog for rows and columns are opened by clicking the corresponding icon in the toolbar.

![Column filter icon in ASP NET pivot client control](Data-Exploration_images/columnfilter.png)

![Row filter icon in ASP NET pivot client control](Data-Exploration_images/rowfilter.png)

The following screenshot displays the Filtering tab in Sorting and Filtering dialog:

![Filtered data in ASP NET pivot client control](Data-Exploration_images/filterdialog.png)

The options in the filtering tab are as follows:

* **Enabling filtering**: Enables/disables the filtering option.
* **Measure**: The measure for filtering is selected from the collection of measures in drop-down list.
* **Condition**: Condition with which the filtering is applied.
* **Value**: Value to compare with each data according to the condition.

The following screenshot displays the data before filtering:

![ASP NET pivot client control](Data-Exploration_images/beforefiltering.png)

The following screenshot displays the data after filtering:

![ASP NET pivot client control is shown with filtered by vaue](Data-Exploration_images/afterfiltering.png)

## Sorting

The Sorting tab in the Sorting And Filtering dialog provides the option to sort the results by rows/columns in the ascending or descending order.

* **Column sorting** - Sorts the columns based on the summary values of each column.
* **Row sorting** - Sorts the rows based on the summary values of each row.

Sorting And Filtering dialog for rows and columns are opened by clicking the corresponding icon in the toolbar.

![Column sort icon in ASP NET pivot client control](Data-Exploration_images/columnsort.png)

![Row sort icon in ASP NET pivot client control](Data-Exploration_images/rowfilter.png)

The following screenshot displays the Sorting And Filtering dialog:

![Sorting dialog in ASP NET pivot client control](Data-Exploration_images/sortdialog.png)

The options in the Sorting tab are as follows:

* **Measure**: The measure for sorting is selected from the collection of measures in drop-down list.
* **Order**: Specifies the sorting order.
* **Preserve Hierarchy**: Sorts the records without changing the hierarchy order.

The following screenshot displays the data after applying the sorting in ascending order for rows:

![ASP NET pivot client control sorted in descending order](Data-Exploration_images/beforesorting.png)

## Grouping

The data can be grouped when more than one-dimension element is added to categorical or series in the axis element builder. Based on the order of addition, the data is grouped and the report is updated. In the following example, members of the **Date** dimension get grouped with respect to members of the **Customer** dimension. Likewise, multiple dimension members can be grouped by dragging the elements from the cube dimension browser to the axis element builder.

![Grouping in ASP NET piot client control](Data-Exploration_images/grouping.png)

## Searching

By clicking the split button of a field, the Member Editor dialog opens through which members are searched and get displayed from the members list in the Member Editor dialog.

![Member editor searching in ASP NET pivot client control](Data-Exploration_images/Searchingbymember.png)
