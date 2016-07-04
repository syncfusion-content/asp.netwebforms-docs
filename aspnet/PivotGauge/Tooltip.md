---
layout: post
title: Tooltip | PivotGauge | ASP.NET | Syncfusion
description: tooltip
platform: aspnet
control: PivotGauge
documentation: ug
---

# Tooltip

Tooltip can be enabled by using the `EnableTooltip` property. By default, this property is set to "false".

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server" EnableTooltip="true">
    </ej:PivotGauge>

{% endhighlight  %}

Tooltip appearance can be customized by overriding its CSS class.

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
