---
layout: post
title: Grouping Bar | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to enable grouping bar feature and its functionalities in ASP.NET PivotGrid control with relational mode
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grouping bar

## Initialization
Grouping bar allows you to dynamically alter the report by filter, sort, and remove operations in the pivot grid control. Based on the relational data source and report bound to the pivot grid control, the grouping bar will be automatically populated. You can enable this option in the pivot grid by setting the `EnableGroupingBar` property to true.

### Client mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableGroupingBar="true" runat="server" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country" SortOrder="Ascending"></ej:Field>
            <ej:Field FieldName="State" FieldCaption="State" SortOrder="Descending"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
        </Columns>
        <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            <ej:Field FieldName="Quantity" FieldCaption="Quantity"></ej:Field>
        </Values>
        <Filters>
            <ej:Field FieldName="Date" FieldCaption="Date">
                <FilterItems FilterType="Exclude" />
            </ej:Field>
        </Filters>
    </DataSource>
    <ClientSideEvents Load="onLoad" />
</ej:PivotGrid>

{% endhighlight %}

![Grouping bar support in ASP NET pivot grid control with relational client mode](Grouping-Bar_images/RealtionalClientGR.png)

### Server mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="/RelationalService" EnableGroupingBar="true">
</ej:PivotGrid>

{% endhighlight %}

![Grouping bar support in ASP NET pivot grid control with relational server mode](Grouping-Bar_images/groupingbar.png)

## Drag and drop

You can alter the report on fly through the drag and drop operation.

![Drag and drop in ASP NET pivot grid control](Grouping-Bar_images/GBar_Rel.png)

## Context menu

You can also alter the report by using the context menu.

![Context menu in ASP NET pivot grid control](Grouping-Bar_images/CMenu_Rel.png)

## Searching values

The search option available in the grouping bar allows you to search a specific value that should be filtered from the list of values in the filter pop-up window.

![Member editor dialog in ASP NET pivot grid control](Grouping-Bar_images/filter.png)

![Searching in ASP NET pivot grid control](Grouping-Bar_images/groupingbar-search.png)

## Filtering values

The filtering option available in the grouping bar allows you to select a specific set of values that should be displayed in the pivot grid control. At least, one value should be present in checked state while filtering, otherwise, the OK button will be disabled.

![Member editor in ASP NET pivot grid control](Grouping-Bar_images/filter.png)

![Filtering in ASP NET pivot grid control](Grouping-Bar_images/filter1.png)

## Sorting values

The sorting option available in the grouping bar allows you to arrange headers in ascending or descending order. This option is applicable for fields available only in the row and column region. By default, headers are sorted in the ascending order. In the sorting indicator, up arrow denotes the ascending order and a down arrow denotes the descending order.

![Sorting icon in ASP NET pivot grid control](Grouping-Bar_images/sort.png)

![Sorted results in ASP NET pivot grid control](Grouping-Bar_images/sort-gird.png)

## Removing field

The remove option available in the grouping bar allows you to completely remove a specific field from the pivot grid control. The remove operation can be achieved by clicking the remove icon available in each field or by dragging and dropping the field out of the grouping bar region.

![Remove icon in ASP NET pivot grid control](Grouping-Bar_images/remove.png)

![Removed items in ASP NET pivot grid control](Grouping-Bar_images/remove-grid.png)


