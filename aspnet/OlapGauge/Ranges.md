---
layout: post
title: Ranges | OLAPGauge | ASP.NET | Syncfusion
description: ranges
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Ranges

## Adding Range Collection

Range collection can be directly added to the scales option within the OlapGauge widget as an array.

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Scales>
        <ej:CircularScales>
            <RangeCollection>
                <ej:CircularRanges DistanceFromScale="10"></ej:CircularRanges>
            </RangeCollection>
        </ej:CircularScales>
    </Scales>
</ej:OlapGauge>

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

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
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
</ej:OlapGauge>

{% endhighlight  %}

![](Ranges_images/range customization.png)

N> On setting both the position properties - "DistanceFromScale" and "Placement" for a range, the value set in "DistanceFromScale" is given preference. 

## Multiple Ranges

Multiple ranges can be added by placing an array of objects in **"Ranges"** option.

{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server">
    <Scales>
        <ej:CircularScales>
            <RangeCollection>
                <ej:CircularRanges StartValue="0" EndValue="10" BackgroundColor="green" DistanceFromScale="-5"></ej:CircularRanges>
                <ej:CircularRanges StartValue="10" EndValue="30" BackgroundColor="yellow" DistanceFromScale="-5"></ej:CircularRanges>
                <ej:CircularRanges StartValue="30" EndValue="50" BackgroundColor="red" DistanceFromScale="-5"></ej:CircularRanges>
            </RangeCollection>
        </ej:CircularScales>
    </Scales>
</ej:OlapGauge>

{% endhighlight %}

![](Ranges_images/multiple ranges.png)
