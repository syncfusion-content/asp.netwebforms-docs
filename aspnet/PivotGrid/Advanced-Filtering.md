---
layout: post
title: Advanced Filtering and Sorting | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to define advance filtering and sorting with respective to the modes in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Advanced filtering and sorting

It allows you to filter and sort the field members in the pivot grid.

### Client mode

In client mode, you can enable the Advanced Filtering and Sorting option in the pivot grid by setting the `EnableAdvancedFilter` property under the `DataSource` to true.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableAdvancedFilter ="true" runat="server">
    <%--...--%>
</ej:PivotGrid>

{% endhighlight %}

### Server mode

In server mode, you can enable the Advanced Filtering and Sorting option in the pivot grid by setting the [`EnableAdvancedFilter`] property to true.

{% highlight html %}

<ej:PivotGrid ID=" PivotGrid1" runat="server" EnableAdvancedFilter ="true">
    <%--...--%>
</ej:PivotGrid>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field either in ascending or descending order.

I> This feature is not applicable for the OLAP data source bound from the server-side.

![Sorting options in ASP NET pivot grid control](AdvanceFiltering_images/sorting.png)

## Label filtering

The label filtering provides an option to filter the members of a field purely based on their caption.

![Label filtering options in ASP NET pivot grid control](AdvanceFiltering_images/filtering.png)

![Label filter dialog in ASP NET pivot grid control](AdvanceFiltering_images/filtering_dialog.png)


## Value filtering

The value filtering provides an option to filter the members based on total values of the appropriate measure between the members of the level.

![Value filtering options in ASP NET pivot grid control](AdvanceFiltering_images/valuefilter.png)

![Value filter dialog in ASP NET pivot grid control](AdvanceFiltering_images/valuefilter_dialog.png)
