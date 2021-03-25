---
layout: post
title: Ticks | PivotGauge | ASP.NET | Syncfusion
description: This document illustrates that how to enable ticks and its customization in ASP.NET PivotGauge control
platform: aspnet
control: PivotGauge
documentation: ug
---

# Ticks

## Adding tick collection

The tick collection can be directly added to the scales option within the pivot gauge control.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <TickCollection>
                    <ej:CircularTicks Type="Major" />
                </TickCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

## Tick customization

The appearance of the tick can be customized through the following properties:

* **Type**: Indicates whether ticks are for major or minor intervals. By default, the type is Major.
* **Height**: Sets the height of the ticks.
* **Width**: Sets the width of the ticks.
* **Angle**: Rotates the ticks to a specified angle. By default, the angle value is 0.
* **Color**: Displays the ticks in specified color.
* **DistanceFromScale**: Sets the distance between the scale and ticks. By default, the values is 0.
* **Placement**: Positions the ticks with respect to the scale.  By default, the value is set to Far.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <TickCollection>
                    <ej:CircularTicks Type="Major" Height="15" Width="4" Angle="0" Color="green" DistanceFromScale="2" Placement="Near" />
                </TickCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![ASPNET PivotGauge Ticks TickCustomizationImage](Ticks_images/TickCustomization.png) 

