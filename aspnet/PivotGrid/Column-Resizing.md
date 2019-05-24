---
layout: post
title:  Column Resizing | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to enable column resizing feature and its customization through API in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Column resizing

Allows you to resize the column by changing its width while holding and dragging the column border by using the mouse.

## Column Width Based on Size

The property `EnableColumnResizing` adjusts the width of each column based on the size of the widget.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableColumnResizing="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %}

## Column Width Based on Text

The property `ResizeColumnsToFit` automatically adjusts the width of each column based on the maximum content length available in the respective column.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" ResizeColumnsToFit="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %}

![Column resizing in ASP NET pivot grid control](Column-Resizing_images/columnresizing.png)
