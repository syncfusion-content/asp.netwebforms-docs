---
layout: post
title: Filtering | TreeGrid | ASP.NET | Syncfusion
description: filtering
platform: aspnet
control: TreeGrid
documentation: ug
---

# Filtering

Filtering helps to view specific or related records from data source which meets a given filtering criteria. To enable filtering in TreeGrid, set `AllowFiltering` as `true`
TreeGrid provides support for the following filtering modes,

* Filter bar
* Menu

Also, the following filtering types are available in TreeGrid

* String
* Boolean
* Date
* Numeric
* Dropdown

The below code explains how to enable filtering in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">
  //...
</ej:TreeGrid>

{% endhighlight %}

The output of the TreeGrid with filtering enabled is as follows.

![](Filtering_images/Filtering_img1.png)


## Filtering Modes

### Filter Bar 

This is the default filtering mode in TreeGrid. It can also be enabled by setting `FilterSettings.FilterType` as `FilterBar`. When this filtering mode is enabled, a filter row will be displayed below the column header, in which we can provide the filter query.

There are two types of actions available to initiate the filtering process in the filter bar mode,

`immediate`- Filtering action will be initiated immediately on key press, for each character being typed in the filter bar.
`onEnter` – Filtering action will be initiated only on enter key press in the filter bar.

The below code snippet explains the above behavior,

{% highlight html %}
 
<ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">         
    //...
    <FilterSettings FilterType="FilterBar"></FilterSettings>
</ej:TreeGrid>

{% endhighlight %}

The output of the filtering with filter bar enabled is as follows.

![](Filtering_images/Filtering_img2.png)

### Menu filtering
Menu filtering can be enabled by setting `FilterSettings.FilterType` property as `Menu`. The below code snippet explains how to enable menu filtering in TreeGrid

{% highlight html %}

<ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">         
    //...
    <FilterSettings FilterType="Menu"></FilterSettings>
</ej:TreeGrid>

{% endhighlight %}

The output of the filtering with filter menu enabled is as follows.

![](Filtering_images/Filtering_img3.png)

## Filtering types
By default, the filtering type for a column is inherited from the `Columns.EditType` property. You can also define a specific filtering type for a column using `Columns.FilterEditType` property.
The below code snippet explains on how to set a filtering type for a column.

{% highlight html %}

<ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">
    <Columns>
        <ej:TreeGridColumn Field="TaskID" EditType="Numeric" AllowFiltering="false" />
        <ej:TreeGridColumn Field="TaskName" EditType="String" FilterEditType="String" />
        <ej:TreeGridColumn Field="FilterStartDate" EditType="Datepicker" FilterEditType="Datepicker"/>
        <ej:TreeGridColumn Field="FilterEndDate" EditType="Datepicker" FilterEditType="Datepicker"/>
        <ej:TreeGridColumn Field="Priority" EditType="Dropdown" FilterEditType="Dropdown" />
        <ej:TreeGridColumn Field="Progress" EditType="Numeric" FilterEditType="Numeric" />                
     </Columns>
     <FilterSettings FilterType="FilterBar"></FilterSettings>
</ej:TreeGrid>

{% endhighlight %}

## Filter columns at initial load
It is also possible to filter one or more columns at load time by providing the field and filter query values to the `FilterSettings.FilteredColumns` property. The following code example explains how to filter a column on initial load.

{% highlight html %}

 <ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">        
     <FilterSettings FilterType="FilterBar">
      <FilteredColumns>
       <ej:TreeGridFilteredColumn Field="TaskName" Operator="StartsWith" Value="plan"/>
      </FilteredColumns>
     </FilterSettings>           
</ej:TreeGrid>

{% endhighlight %}

## Disabling filtering for a specific column 
It is possible to disable filtering for a specific column by setting `Columns.AllowFiltering` as `false` in the column definition.
The below code snippet explains the above behavior

{% highlight html %}
<ej:TreeGrid ID="TreeGridControlFiltering" AllowFiltering="true">
    <Columns>
        <ej:TreeGridColumn Field="TaskID" AllowFiltering="false" />            
     </Columns>
     //...
</ej:TreeGrid>

{% endhighlight %}

The output of the filtering enabled for only one column is as follows.

![](Filtering_images/Filtering_img4.png)

[Click here](http://asp.syncfusion.com/demos/web/treegrid/treegridcolumnfiltering.aspx) to find the demo sample for filtering in TreeGrid
