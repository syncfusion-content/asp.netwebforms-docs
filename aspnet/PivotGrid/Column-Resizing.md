---
layout: post
title:  Column Resizing | PivotGrid | ASP.NET | Syncfusion
description: column resizing
platform: aspnet
control: PivotGrid
documentation: ug
---

# Column resizing

Allows you to resize the column by changing its width while holding and dragging the column border by using the mouse.

You can enable the column resizing option in the pivot grid by setting the `EnableColumnResizing` property to true.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableColumnResizing="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %} 

![](Column-Resizing_images/columnresizing.png)