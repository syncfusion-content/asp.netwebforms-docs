---
layout: post
title:  Frozen Header | PivotGrid | ASP.NET | Syncfusion
description:  frozen header
platform: aspnet
control: PivotGrid
documentation: ug
---

# Frozen header

Allows you to freeze the header of the grid, so that it will be always visible when scrolling the content with a large number of rows or columns to provide a precise view.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
    <FrozenHeaderSettings EnableFrozenHeaders="true"></FrozenHeaderSettings>
</ej:PivotGrid>

{% endhighlight %}

![](FrozenHeader_images/row_col_freeze.png)

You can also freeze the row/column headers individually by setting the below properties:

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
    <FrozenHeaderSettings EnableFrozenRowHeaders="true"></FrozenHeaderSettings> //To Freeze the Row headers
</ej:PivotGrid>

{% endhighlight %}

![](FrozenHeader_images/row_freeze.png)

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
    <FrozenHeaderSettings EnableFrozenColumnHeaders="true"></FrozenHeaderSettings> //To Freeze the Column headers
</ej:PivotGrid>
    
{% endhighlight %}

![](FrozenHeader_images/col_freeze.png)