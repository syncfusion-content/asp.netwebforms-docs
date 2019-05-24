---
layout: post
title: Responsive | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to enable responsive layout rendering in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Responsive

The pivot grid and pivot table field list control support responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot grid by setting the `IsResponsive` property to true.

When resizing the browser, the pivot table field list will be collapsed, and an icon will appear on the left-hand side of the browser. You can toggle its view and perform UI interaction.

{% highlight CSHTML %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="/PivotGridService.svc" IsResponsive="true"></ej:PivotGrid>

{% endhighlight %}

![ASP NET pivot grid control with normal layout](Responsive-Layout_images/normal.png)

_Normal PivotGrid_

![ASP NET pivot grid control with responsive layout](Responsive-Layout_images/responsive.png)

_Responsive PivotGrid_

![ASP NET pivot table field list in collapsed state](Responsive-Layout_images/res-schema.png)

_Responsive PivotTable Field List - Collapsed_

![ASP NET pivot table field list in expanded state](Responsive-Layout_images/res-schema1.png)

_Responsive PivotTable Field List - Expanded_

