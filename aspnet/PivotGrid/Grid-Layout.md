---
layout: post
title: Grid Layout | PivotGrid | ASP.NET | Syncfusion
description: grid layout
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grid Layout

I> This feature is applicable only for OLAP datasource only at Server Mode.

## Normal Layout

A layout in which summary cells are positioned at the bottom of each parent member and their child members appear next to them. Normal layout is the default layout in PivotGrid control. The enumeration property `Layout` needs to be set to **"Normal"** in-order to view PivotGrid in normal layout. 

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../PivotGridService" Layout="Normal"></ej:PivotGrid>

{% endhighlight %}

![](Grid-Layout_images/layout-normal.png) 

## No Summaries Layout

A layout in which summary cells are completely hidden and the child members appear next to their parent member.  The enumeration property `Layout` needs to be set to **"NoSummaries"** in-order to view PivotGrid without summaries. 

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../PivotGridService" Layout="NoSummaries"></ej:PivotGrid>

{% endhighlight %}

![](Grid-Layout_images/layout-nosummary.png) 


## Excel-like Layout

A layout in which summary cells are positioned besides each parent member and their child members appear next to them. The enumeration property `Layout` needs to be set to **"ExcelLikeLayout"** in-order to view PivotGrid in excel-like layout.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../PivotGridService" Layout="ExcelLikeLayout"></ej:PivotGrid>

{% endhighlight %}

![](Grid-Layout_images/layout-excel.png) 	

## Top Summary Layout 

A layout in which summary cells are positioned at the top of each parent member and their child members appear next to them. The enumeration property `Layout` needs to be set to **"NormalTopSummary"** in-order to view PivotGrid in top summaries layout.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../PivotGridService" Layout="NormalTopSummary"></ej:PivotGrid>

{% endhighlight %}

![](Grid-Layout_images/layout-top.png)  

