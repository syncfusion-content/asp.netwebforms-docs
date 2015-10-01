---
layout: post
title: Indicators | LinearGauge | ASP.NET Webforms | Syncfusion
description: indicators
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Indicators

Indicators simply indicates the current status of the pointer. Indicators are in several formats such as in shape format, textual format and image format.

## Setting Dimension

* You can enable indicators by setting showIndicators to ‘true’ in scale collection. The height and width property for the indicators are used to specify the area allocated to the indicator for the width and height respectively. 
* You can use the position collection to position the indicators along X and Y axis. X specifies horizontal position in indicators whereas Y specifies vertical position in indicators. Indicators are of several types such as, dimensions like circle, rectangle, rounded rectangle, text and image. By using the type property it can be applied. For image type imageUrl property is used.

{% highlight html %}

<%--For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false">

<Scales>

<ej:Scales Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowBarPointers="false">

<Border Color="transparent" Width="0" />

<MarkerPointerCollection>

<ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="-4"></ej:MarkerPointers>

</MarkerPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="20" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="20" Y="0" />

</ej:LinearTicks>

</TickCollection>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="3" Y="0" />

</ej:Labels>

</LabelCollection>

<%--Setting indicator-- %>

<IndicatorCollection>

<ej:Indicators Height="10" Width="10" type="Circle">

<Position X="49" Y="100" />

</ej:Indicators>

</IndicatorCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Indicators_images/Indicators_img1.png)



## State Ranges

State ranges are used to specify the indicator behavior in the certain region. startValue and endValue are used to set the range bound for the pointer. Whenever the pointer crosses the specified region, the indicator attributes are applied for the ranges.


{% highlight html %}

<%--For linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false">

<Scales>

<ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowRanges="true" ShowIndicators="true" ShowBarPointers="false">

<Border Color="transparent" Width="0" />

<MarkerPointerCollection>

<ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"></ej:MarkerPointers>

</MarkerPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-12" Y="0" />

</ej:Labels>

</LabelCollection>

<RangeCollection>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361">

<Border Color="#94C361"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67">

<Border Color="#F9CF67"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83">

<Border Color="#F89B83"  Width="1" />

</ej:Ranges>

</RangeCollection>

<IndicatorCollection>

<ej:Indicators Height="10" Width="10" type="Circle">

<Position X="49" Y="100" />

<%--Setting range backgroundcolor, range end value and start value-- %>

<StateRangeCollection>

<ej:StateRanges StateRangeBackgroundColor="#02A258" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="#02A258" />

<ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="grey" />

</StateRangeCollection>

</ej:Indicators>

</IndicatorCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Indicators_images/Indicators_img2.png)



## Color and Appearance

The backgroundColor and borderColor sets the appearance behavior for the indicators. You can apply this only if it lies within the state ranges. Otherwise default behavior will be applied.

{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false">

<%-- For setting Scales-- %>

<Scales>

<ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowBarPointers="false">

<Border Color="transparent" Width="0" />

<MarkerPointerCollection>

<ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"></ej:MarkerPointers>

</MarkerPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-12" Y="0" />

</ej:Labels>

</LabelCollection>

<%--Setting Indicator height, width, type and position-- %>

<IndicatorCollection>

<ej:Indicators Height="10" Width="10" type="Circle">

<Position X="49" Y="100" />

<StateRangeCollection>

<ej:StateRanges StateRangeBackgroundColor="#91B64E" StateRangeEndValue="300" StateRangeStartValue="0" StateRangeBorderColor="#91B64E" />

</StateRangeCollection>

</ej:Indicators>

</IndicatorCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Indicators_images/Indicators_img3.png)



## Font options

The basic font options available for the textual type indicators in the Linear Gauge such as Size, font style and font family are achieved by the properties size, fontStyle and fontFamily.

{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false">

<%-- For setting scales-- %>

<Scales>

<ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowRanges="true" ShowIndicators="true" ShowBarPointers="false">

<Border Color="transparent" Width="0" />

<%-- For setting marker pointers-- %>

<MarkerPointerCollection>

<ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"></ej:MarkerPointers>

</MarkerPointerCollection>

<%-- For setting Ticks-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- For setting labels-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-12" Y="0" />

</ej:Labels>

</LabelCollection>

<%-- For setting ranges-- %>

<RangeCollection>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361">

<Border Color="#94C361"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67">

<Border Color="#F9CF67"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83">

<Border Color="#F89B83"  Width="1" />

</ej:Ranges>

</RangeCollection>

<IndicatorCollection>

<ej:Indicators type="text">

<TextLocation X="50" Y="100" />

<%--Setting indicator font size, fontfamily and font style-- %>

<Font Size="12px" FontFamily="arial" FontStyle="bold"></Font>

<StateRangeCollection>

<ej:StateRanges StateRangeEndValue="200" StateRangeStartValue="0"  StateRangetext="Safe"  StateRangetextColor="#94C361"/>

<ej:StateRanges StateRangeEndValue="250" StateRangeStartValue="200" StateRangetext="Caution" StateRangetextColor="#F9CF67"/>

<ej:StateRanges StateRangeEndValue="300" StateRangeStartValue="250" StateRangetext="Danger" StateRangetextColor="#F89B83"/>

</StateRangeCollection>

</ej:Indicators>

</IndicatorCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Indicators_images/Indicators_img4.png)



## Multiple Indicator

You can set multiple indicators in a single Linear Gauge by adding an array of indicator objects. Refer the following code example for multiple indicator functionality.

{% highlight html %}

<ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false">

<%-- For setting scale collection-- %>

<Scales>

<ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowRanges="true" ShowBarPointers="false">

<Border Color="transparent" Width="0" />

<MarkerPointerCollection>

<ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"></ej:MarkerPointers>

</MarkerPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-12" Y="0" />

</ej:Labels>

</LabelCollection>

<RangeCollection>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361">

<Border Color="#94C361"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67">

<Border Color="#F9CF67"  Width="1" />

</ej:Ranges>

<ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83">

<Border Color="#F89B83"  Width="1" />

</ej:Ranges>

</RangeCollection>

<IndicatorCollection>

<%--Setting indicator1-- %>

<%-- For setting indicator type-- %>

<ej:Indicators Height="10" Width="10" type="Circle">

<Position X="30" Y="100" />

<%-- For setting state range collection-- %>

<StateRangeCollection>

<ej:StateRanges StateRangeBackgroundColor="#02A258" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="#02A258" />

<ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="grey" />

</StateRangeCollection>

</ej:Indicators>

<%--Setting indicator2-- %>



<ej:Indicators Height="10" Width="10" type="Circle">

<Position X="70" Y="100" />

<StateRangeCollection>

<ej:StateRanges StateRangeBackgroundColor="red" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="red" />

<ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="grey" />

</StateRangeCollection>

</ej:Indicators>

</IndicatorCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}


Execute the above code to render the following output.

![](Indicators_images/Indicators_img5.png)