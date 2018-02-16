---
layout: post
title: Value-Soritng | PivotClient | ASP.NET | Syncfusion
description: value sorting
platform: aspnet
control: PivotClient
documentation: ug
---

# Value Sorting

I> This feature is applicable for Relational datasource.

Value Sorting allows to sort columns and rows based on value fields.

The headers of the column to be sorted is given in the 'HeaderText' property under 'ValueSortSettings' in field wise order separated by a string.  The string which is used to separate the headers is given in the property 'HeaderDelimiters'.
Also you can sort column by clicking the column header. On clicking the same header once again will reverse the sorting direction.

{% highlight js %}
  
<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
        </Columns>
        <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            <ej:Field FieldName="Quantity" FieldCaption="Quantity"></ej:Field>
        </Values>
    </DataSource>
    <ValueSortSettings HeaderText="Bike##Quantity" HeaderDelimiters="##" SortOrder="Descending" />
</ej:PivotClient>

{% endhighlight %}

![](Value-Sorting_images/Before.png) 

![](Value-Sorting_images/After.png) 



