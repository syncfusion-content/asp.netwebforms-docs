---
layout: post
title: Frame Type | PivotGauge | ASP.NET | Syncfusion
description: frame type 
platform: aspnet
control: PivotGauge
documentation: ug
---

# Frame Type

## Full Circle

Full Circle frame lets the PivotGauge display in circular shape. Frame type can be set using the `FrameType` property.  By default, the frame type is "FullCircle". 

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Frame FrameType="FullCircle" />
    </ej:PivotGauge>

{% endhighlight  %}

![](Frame-Type/FullCircle.png) 

## Half Circle

Half Circle frame lets the PivotGauge display in semi-circular shape. For this, frame type needs to be set as "HalfCircle" within the `FrameType` property.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Frame FrameType="HalfCircle" />
    </ej:PivotGauge>

{% endhighlight  %}

![](Frame-Type/HalfCircle.png) 
