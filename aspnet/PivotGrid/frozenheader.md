---
layout: post
title:  Frozen Header | PivotGrid | ASP.NET | Syncfusion
description:  This document illustrates that how to enable frozen header feature and its options in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Frozen header

Allows you to freeze the header of the grid, so that it will be always visible when scrolling the content with a large number of rows or columns to provide a precise view.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <%--...--%>
    <FrozenHeaderSettings EnableFrozenHeaders="true"></FrozenHeaderSettings>
</ej:PivotGrid>

{% endhighlight %}

![Frozen header, aka Freeze headers support in ASP NET pivot grid control](FrozenHeader_images/row_col_freeze.png)

You can also freeze the row/column headers individually by setting the below properties:

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <%--...--%>
    <FrozenHeaderSettings EnableFrozenRowHeaders="true"></FrozenHeaderSettings>  <%--To Freeze the Row headers--%>
</ej:PivotGrid>

{% endhighlight %}

![Frozen row headers in ASP NET pivot grid control](FrozenHeader_images/row_freeze.png)

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <%--...--%>
    <FrozenHeaderSettings EnableFrozenColumnHeaders="true"></FrozenHeaderSettings> <%--To Freeze the Column headers--%>
</ej:PivotGrid>

{% endhighlight %}

![Frozen column headers in ASP NET pivot grid control](FrozenHeader_images/col_freeze.png)

We can also set the size of the scroller (horizontal and vertical) in PivotGrid by using below property.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <%--...--%>
    <FrozenHeaderSettings ScrollerSize=18></FrozenHeaderSettings>
</ej:PivotGrid>

{% endhighlight %}

![Scroller size in ASP NET pivot grid control](FrozenHeader_images/scroll_size.png)