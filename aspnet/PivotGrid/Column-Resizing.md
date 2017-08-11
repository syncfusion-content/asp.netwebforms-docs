---
layout: post
title:  Column Resizing | PivotGrid | ASP.NET | Syncfusion
description: column resizing
platform: aspnet
control: PivotGrid
documentation: ug
---

# Resizing Column

Allows the user to change the column width by holding and dragging the column border using the mouse pointer.

You can enable the resizing option in PivotGrid by setting the `EnableColumnResizing` property to true.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableColumnResizing="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %} 

![](Column-Resizing_images/columnresizing.png)


Additionally, the property `ResizeColumnsToFit` automatically adjusts the width of each column based on the maximum content length available in the respective column.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableColumnResizing="true" ResizeColumnsToFit="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %} 