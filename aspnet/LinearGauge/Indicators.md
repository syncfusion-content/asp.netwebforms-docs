---
layout: post
title: Indicators
description: indicators
platform: common
control: Linear Gauge
documentation: ug
---

# Indicators

Indicators simply indicates the current status of the pointer. Indicators are in several formats such as in shape format, textual format and image format.

## Setting Dimension

* You can enable indicators by setting showIndicators to ‘true’ in scale collection. The height and width property for the indicators are used to specify the area allocated to the indicator for the width and height respectively. 
* You can use the position collection to position the indicators along X and Y axis. X specifies horizontal position in indicators whereas Y specifies vertical position in indicators. Indicators are of several types such as, dimensions like circle, rectangle, rounded rectangle, text and image. By using the type property it can be applied. For image type imageUrl property is used.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="-4"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="20" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="20" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="3" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%--Setting indicator-- %&gt;

&lt;IndicatorCollection&gt;

&lt;ej:Indicators Height="10" Width="10" type="Circle"&gt;

&lt;Position X="49" Y="100" /&gt;

&lt;/ej:Indicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Indicators_images/Indicators_img1.png)
{:.image }


## State Ranges

State ranges are used to specify the indicator behavior in the certain region. startValue and endValue are used to set the range bound for the pointer. Whenever the pointer crosses the specified region, the indicator attributes are applied for the ranges.



[ASP]

&lt;%--For linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowRanges="true" ShowIndicators="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361"&gt;

&lt;Border Color="#94C361"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67"&gt;

&lt;Border Color="#F9CF67"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83"&gt;

&lt;Border Color="#F89B83"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;IndicatorCollection&gt;

&lt;ej:Indicators Height="10" Width="10" type="Circle"&gt;

&lt;Position X="49" Y="100" /&gt;

&lt;%--Setting range backgroundcolor, range end value and start value-- %&gt;

&lt;StateRangeCollection&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="#02A258" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="#02A258" /&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="grey" /&gt;

&lt;/StateRangeCollection&gt;

&lt;/ej:Indicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Indicators_images/Indicators_img2.png)
{:.image }


## Color and Appearance

The backgroundColor and borderColor sets the appearance behavior for the indicators. You can apply this only if it lies within the state ranges. Otherwise default behavior will be applied.


[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false"&gt;

&lt;%-- For setting Scales-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%--Setting Indicator height, width, type and position-- %&gt;

&lt;IndicatorCollection&gt;

&lt;ej:Indicators Height="10" Width="10" type="Circle"&gt;

&lt;Position X="49" Y="100" /&gt;

&lt;StateRangeCollection&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="#91B64E" StateRangeEndValue="300" StateRangeStartValue="0" StateRangeBorderColor="#91B64E" /&gt;

&lt;/StateRangeCollection&gt;

&lt;/ej:Indicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Indicators_images/Indicators_img3.png)
{:.image }


## Font options

The basic font options available for the textual type indicators in the Linear Gauge such as Size, font style and font family are achieved by the properties size, fontStyle and fontFamily.

[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;%-- For setting scales-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowRanges="true" ShowIndicators="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;%-- For setting marker pointers-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For setting Ticks-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For setting labels-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%-- For setting ranges-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361"&gt;

&lt;Border Color="#94C361"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67"&gt;

&lt;Border Color="#F9CF67"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83"&gt;

&lt;Border Color="#F89B83"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;IndicatorCollection&gt;

&lt;ej:Indicators type="text"&gt;

&lt;TextLocation X="50" Y="100" /&gt;

&lt;%--Setting indicator font size, fontfamily and font style-- %&gt;

&lt;Font Size="12px" FontFamily="arial" FontStyle="bold"&gt;&lt;/Font&gt;

&lt;StateRangeCollection&gt;

&lt;ej:StateRanges StateRangeEndValue="200" StateRangeStartValue="0"  StateRangetext="Safe"  StateRangetextColor="#94C361"/&gt;

&lt;ej:StateRanges StateRangeEndValue="250" StateRangeStartValue="200" StateRangetext="Caution" StateRangetextColor="#F9CF67"/&gt;

&lt;ej:StateRanges StateRangeEndValue="300" StateRangeStartValue="250" StateRangetext="Danger" StateRangetextColor="#F89B83"/&gt;

&lt;/StateRangeCollection&gt;

&lt;/ej:Indicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Indicators_images/Indicators_img4.png)
{:.image }


## Multiple Indicator

You can set multiple indicators in a single Linear Gauge by adding an array of indicator objects. Refer the following code example for multiple indicator functionality.

[ASP]



&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;%-- For setting scale collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="0" Minimum="0" Maximum="300" MinorIntervalValue="5" MajorIntervalValue="30" BackgroundColor="transparent" ShowIndicators="true" ShowRanges="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="0" EndValue="200" RangeBackgroundColor="#94C361"&gt;

&lt;Border Color="#94C361"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="200" EndValue="250" RangeBackgroundColor="#F9CF67"&gt;

&lt;Border Color="#F9CF67"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartWidth="5" EndWidth="5" StartValue="250" EndValue="300" RangeBackgroundColor="#F89B83"&gt;

&lt;Border Color="#F89B83"  Width="1" /&gt;

&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;IndicatorCollection&gt;

&lt;%--Setting indicator1-- %&gt;

&lt;%-- For setting indicator type-- %&gt;

&lt;ej:Indicators Height="10" Width="10" type="Circle"&gt;

&lt;Position X="30" Y="100" /&gt;

&lt;%-- For setting state range collection-- %&gt;

&lt;StateRangeCollection&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="#02A258" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="#02A258" /&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="grey" /&gt;

&lt;/StateRangeCollection&gt;

&lt;/ej:Indicators&gt;

&lt;%--Setting indicator2-- %&gt;



&lt;ej:Indicators Height="10" Width="10" type="Circle"&gt;

&lt;Position X="70" Y="100" /&gt;

&lt;StateRangeCollection&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="red" StateRangeEndValue="300" StateRangeStartValue="200" StateRangeBorderColor="red" /&gt;

&lt;ej:StateRanges StateRangeBackgroundColor="grey" StateRangeEndValue="200" StateRangeStartValue="0" StateRangeBorderColor="grey" /&gt;

&lt;/StateRangeCollection&gt;

&lt;/ej:Indicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.



![](Indicators_images/Indicators_img5.png)
{:.image }


