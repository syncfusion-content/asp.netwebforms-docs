---
layout: post
title: Tooltip | OLAPGauge | ASP.NET | Syncfusion
description: tooltip
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Tooltip

Tooltip can be enabled by using the `EnableTooltip` property. By default, this property is set to "false".

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server" EnableTooltip="true">
</ej:OlapGauge>

{% endhighlight  %}

Tooltip appearance can be customized by overriding its CSS class.

{% highlight css %}

.e-olapgauge-tooltip {
    background-color: aqua!important;
    border: 2 px solid red!important;
    color: black!important;
    border-radius: 18 px!important;
    margin-top: 20 px;
    text-align: left;
    font: 12 px Segoe UI;
    line-height: 20 px;
}

{% endhighlight %}

![](Tooltip_images/tooltip.png) 
