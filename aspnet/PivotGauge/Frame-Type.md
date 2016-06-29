---
layout: post
title: Frame Type | OLAPGauge | ASP.NET | Syncfusion
description: frame type 
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Frame Type

## Full Circle

Full Circle frame lets the OlapGauge display in circular shape. Frame type can be set using the `FrameType` property.  By default, the frame type is "FullCircle". 

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Frame FrameType="FullCircle" />
</ej:OlapGauge>

{% endhighlight  %}

![](Frame-Type_images/fullCircle.png) 

## Half Circle

Half Circle frame lets the OlapGauge display in semi-circular shape. For this, frame type needs to be set as "HalfCircle" within the `FrameType` property.

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Frame FrameType="HalfCircle" />
</ej:OlapGauge>

{% endhighlight  %}

![](Frame-Type_images/halfCircle.png) 
