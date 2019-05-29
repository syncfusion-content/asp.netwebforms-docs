---
layout: post
title: Tooltip | PivotGauge | ASP.NET | Syncfusion
description: This document illustrates that how to enable Tooltip and its customization in ASP.NET PivotGauge control
platform: aspnet
control: PivotGauge
documentation: ug
---

# Tooltip

The tooltip can be enabled by using the `EnableTooltip` property. 

N> By default, the property is set to false.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server" EnableTooltip="true">
    </ej:PivotGauge>

{% endhighlight  %}

The tooltip appearance can be customized by overriding its CSS class.

{% highlight css %}

    .e-pivotgauge-tooltip {
        background-color: #D2E9FE!important;
        border: 2px solid #01465C!important;
        color: #01232E!important;
        border-radius: 5px!important;
        margin-top: 20px;
        text-align: left;
        font: 12 px Segoe UI;
        line-height: 20px;
    }

{% endhighlight %}

![](Tooltip_images/Tooltip.png) 
