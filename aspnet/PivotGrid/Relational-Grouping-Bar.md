---
layout: post
title: Grouping Bar | PivotGrid | ASP.NET | Syncfusion
description: grouping bar
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grouping Bar

## Initialization 
Grouping Bar allows user to dynamically alter the report by filter, sort and remove operations in the PivotGrid control. Based on the Relational datasource and report bound to the PivotGrid control, Grouping Bar will be automatically populated. You can enable Grouping Bar option in PivotGrid by setting the `EnableGroupingBar` property to true.

### Client Mode

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

![](Grouping-Bar_images/RealtionalClientGR.png)

### Server Mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="/RelationalService" EnableGroupingBar="true">
</ej:PivotGrid>

{% endhighlight %}

![](Grouping-Bar_images/groupingbar.png)

## Drag and Drop

You can alter the report on fly through drag-and-drop operation.

![](Grouping-Bar_images/GBar_Rel.png)

## Context Menu

You can also alter the report by using context menu.

![](Grouping-Bar_images/CMenu_Rel.png)

## Searching Values

Search option available in Grouping Bar allows you to search a specific value that needs to be filtered from the list of values inside the filter pop-up window.

![](Grouping-Bar_images/filter.png)

![](Grouping-Bar_images/groupingbar-search.png)

## Filtering Values

Filtering option available in Grouping Bar allows you to select a specific set of values that needs to be displayed in the PivotGrid control. At least one value needed to be in checked state while filtering otherwise “Ok” button will be disabled.

![](Grouping-Bar_images/filter.png)

![](Grouping-Bar_images/filter1.png)

## Sorting Values

Sorting option available in Grouping Bar allows you to arrange headers either in ascending or descending order. Sorting option is applicable for fields available only in Row and Column region. By default, headers are sorted in ascending order. Regarding sorting indicator, up arrow denotes ascending order and down arrow denotes descending order.

![](Grouping-Bar_images/sort.png)

![](Grouping-Bar_images/sort-gird.png)

## Removing Field

Remove option available in the Grouping Bar allows you to completely remove a specific field from the PivotGrid control. Remove operation can be either achieved by clicking remove icon available inside each field or by dragging and dropping field out of Grouping Bar region.

![](Grouping-Bar_images/remove.png)

![](Grouping-Bar_images/remove-grid.png)


