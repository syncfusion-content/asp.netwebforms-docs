---
layout: post
title: Scale | OLAPGauge | ASP.NET | Syncfusion
description: scale
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Scale

## Adding Scale

Scale can be added within the OlapGauge widget as an array.

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Scales>
        <ej:CircularScales Radius="150"></ej:CircularScales>
    </Scales>
</ej:OlapGauge>

{% endhighlight  %}

![](Scales_images/scale.png) 

## Scale Customization

### Pointer Cap

Pointer Cap is a circular shape element that is located at the center of the OlapGauge. It can be customized with the `PointerCap` option inside scales. Following are the properties used to customize its appearance.

* **Radius** – sets the radius of the pointer cap.
* **BorderColor** – sets the color of the pointer cap border.
* **BorderWidth** – sets the width of the pointer cap border.
* **BackgroundColor** – sets the background color of the pointer cap.

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Scales>
        <ej:CircularScales Radius="150">
            <PointerCap BackgroundColor="yellow" BorderColor="green" Radius="5" BorderWidth="2"></PointerCap>
        </ej:CircularScales>
    </Scales>
</ej:OlapGauge>

{% endhighlight  %}

![](Scales_images/pointercap.png)

### Appearance
The appearance of the scale can be customized through the following properties.

* **Radius** – sets the radius of the scale.
* **BackgroundColor** – sets the background color of the scale.
* **Border** – sets the border of the scale with color and width properties.
* **Size** – sets the size of the scale.
* **Minimum** – sets the least value of the scale.
* **Maximum** – sets the highest value of the scale.
* **MajorIntervalValue** – sets the interval between minor ticks in the scale.
* **MinorIntervalValue** – sets the interval between major ticks in the scale.
* **Direction** – sets the direction of the scale.  By default it takes “Clockwise” direction.

The `ShowIndicators`, `ShowTicks`, `ShowRanges`, `ShowPointers` and `ShowScaleBar` properties are used to enable/disable the indicators, ticks, ranges, pointers and scale bar respectively.  By default, these properties are set to true. 

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Scales>
        <ej:CircularScales Radius="120" BackgroundColor="yellow" Size="10" Minimum="20" Maximum="120" MajorIntervalValue="20" MinorIntervalValue="5" Direction="CounterClockwise">
            <Border Color="blue" Width="3" />
        </ej:CircularScales>
    </Scales>
</ej:OlapGauge>

{% endhighlight  %}

![](Scales_images/Scale-Customization-Appearance.png)
