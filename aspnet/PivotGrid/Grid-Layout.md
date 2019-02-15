---
layout: post
title: Grid Layout | PivotGrid | ASP.NET | Syncfusion
description: grid layout
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grid layout

## Normal layout

A layout in summary cells, which are positioned at the bottom of each parent member and their child members appear next to them. Normal layout is the default layout in the pivot grid control. The `Layout` enumeration property should be set to **"Normal"** to view the pivot grid in normal layout.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="/PivotGridService.svc" Layout="Normal"></ej:PivotGrid>

{% endhighlight %}

![Normal layout in ASP NET pivot grid control](Grid-Layout_images/layout-normal.png)

## No summaries layout

I> This feature is applicable only for the OLAP data source.

A layout in summary cells, which are completely hidden and the child members appear next to their parent member. The `Layout` enumeration property should be set to **"NoSummaries"** to view the pivot grid without summaries.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="/PivotGridService.svc" Layout="NoSummaries"></ej:PivotGrid>

{% endhighlight %}

![No summaries layout in ASP NET pivot grid control](Grid-Layout_images/layout-nosummary.png)


## Excel-like layout

A layout in summary cells, which are positioned besides each parent member and their child members appear next to them. The `Layout` enumeration property should be set to **"ExcelLikeLayout"** to view the pivot grid in Microsoft Excel.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="/PivotGridService.svc" Layout="ExcelLikeLayout"></ej:PivotGrid>

{% endhighlight %}

![Excel like layout in ASP NET pivot grid control](Grid-Layout_images/layout-excel.png)

## Top summary Layout

I> This feature is applicable only for the OLAP data source at server mode.

A layout in summary cells, which are positioned at the top of each parent member and their child members appear next to them. The `Layout` enumeration property should be set to **"NormalTopSummary"** to view the pivot grid in the top summaries layout.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="/PivotGridService.svc" Layout="NormalTopSummary"></ej:PivotGrid>

{% endhighlight %}

![Top summary layout in ASP NET pivot grid control](Grid-Layout_images/layout-top.png)

