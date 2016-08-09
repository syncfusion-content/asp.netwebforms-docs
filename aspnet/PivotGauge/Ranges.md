---
layout: post
title: Ranges | PivotGauge | ASP.NET | Syncfusion
description: ranges
platform: aspnet
control: PivotGauge
documentation: ug
---

# Ranges

## Adding Range Collection

`RangeCollection` can be directly added to the scales option within the PivotGauge control.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <RangeCollection>
                    <ej:CircularRanges DistanceFromScale="10"></ej:CircularRanges>
                </RangeCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight  %}

## Appearance Customization

The appearance of the range can be customized through the following properties.

* **StartValue** – defines the start position of the range.
* **EndValue** – defines the end position of the range.
* **StartWidth** – sets the width at starting position of the range.
* **EndWidth** – sets the width at ending position of the range.
* **BackgroundColor** – sets the background color of the range.
* **Border** – sets the height and width of the border of the range.
* **Placement** – sets the position of the range.
* **DistanceFromScale** – sets the distance between the range and scale.

Positioning the range could be set either through `Placement` or `DistanceFromScale` property. 

N> By default, placement takes the value “near”, whereas other enumeration values available are “far” and “center”.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <RangeCollection>
                    <ej:CircularRanges StartValue="20" EndValue="50" StartWidth="2" EndWidth="6" BackgroundColor="yellow" DistanceFromScale="20">
                        <Border Color="red" Width="2" />
                    </ej:CircularRanges>
                    <ej:CircularRanges StartValue="50" EndValue="100" StartWidth="2" EndWidth="7" BackgroundColor="blue" Placement="Near">
                        <Border Color="green" Width="2" />
                    </ej:CircularRanges>
                </RangeCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight  %}

![](Ranges_images/AppearanceCustomization.png)

N> On setting both the position properties - "DistanceFromScale" and "Placement" for a range, the value set in "DistanceFromScale" is given preference. 

## Multiple Ranges

Multiple ranges can be added in `RangeCollection` to the scales option within the PivotGauge control.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <RangeCollection>
                    <ej:CircularRanges StartValue="0" EndValue="10" BackgroundColor="green" DistanceFromScale="-5"></ej:CircularRanges>
                    <ej:CircularRanges StartValue="10" EndValue="30" BackgroundColor="yellow" DistanceFromScale="-5"></ej:CircularRanges>
                    <ej:CircularRanges StartValue="30" EndValue="50" BackgroundColor="red" DistanceFromScale="-5"></ej:CircularRanges>
                </RangeCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Ranges_images/MultipleRanges.png)
