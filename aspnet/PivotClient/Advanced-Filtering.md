---
layout: post
title: Advanced Filtering and Sorting | ASP.NET PivotClient | Syncfusion
description: This document illustrates that how to define advance filtering and sorting with respective to the modes in ASP.NET PivotClient control
platform: aspnet
control: PivotClient
documentation: ug
---

# Advanced filtering and sorting

It allows to filter and sort the field members in the pivot client.

### Client mode

In client mode, you can enable the advanced filtering and sorting option in the pivot client by setting the `EnableAdvancedFilter` property under the `DataSource` to true.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server">
    <DataSource EnableAdvancedFilter ="true">
        <%--...--%>
    </DataSource>
</ej:PivotClient>

{% endhighlight %}

### Server mode

In server mode, you can enable the advanced filtering and sorting option in the pivot client by setting the `EnableAdvancedFilter` property to true.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server" EnableAdvancedFilter ="true">
    <%--...--%>
</ej:PivotClient>

{% endhighlight %}

## Sorting

The sorting provides an option to sort the members of a field in ascending or descending order.

I> This option is not applicable for the OLAP data source bound from the server-side.

![Sorting options in ASP NET pivot client control](AdvanceFiltering_images/sorting.png)

## Label filtering

The label filtering provides an option to filter the members of a field purely based on their caption.

![Label filtering options in ASP NET pivot client control](AdvanceFiltering_images/filtering.png)

![Label filter dialog in ASP NET pivot client control](AdvanceFiltering_images/filtering_dialog.png)

## Value filtering

The value filtering provides an option to filter members based on total values of the appropriate measure between the members of the level.

![Value filtering options in ASP NET pivot client control](AdvanceFiltering_images/valuefilter.png)

![Value filter dialog in ASP NET pivot client control](AdvanceFiltering_images/valuefilter_dialog.png)