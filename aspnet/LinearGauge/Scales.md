---
layout: post
title: Scales
description: scales
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Scales

Scales are the basic functional block of the Linear Gauge. You can improve the appearance of scales by customizing it. The functional blocks of Linear Gauge are 

* Marker Pointers
* Bar Pointer
* Labels
* Custom Labels
* Indicators
* Ticks
* Ranges



Adding multiple scales

You can set multiple scales for a single Linear Gauge control by using an array of scale objects. Each scale object is independent of each other. Refer the following code example to add multiple scale collection. 

[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false"&gt;

&lt;%-- For adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;%-- Adding Scale1-- %&gt;

&lt;ej:Scales width="8" BackgroundColor="Grey" ShowMarkerPointers="true" ShowBarPointers="false"&gt;

&lt;Position X="15" Y="50" /&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282"&gt; &lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;



&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="50" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- Adding scale2 -- %&gt;

&lt;Scales&gt;

&lt;ej:Scales width="8" direction="Clockwise" BackgroundColor="#206BA4" ShowMarkerPointers="false" ShowLabels="false" ShowBarPointers="false"&gt;

&lt;Position X="90" Y="50" /&gt;

&lt;Border Color="#206BA4" Width="1" /&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" placement="Far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far" &gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- Adding scale3-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales width="18" type="Thermometer" length="300" BackgroundColor="#C0B08E" ShowTicks="false" ShowMarkerPointers="false" ShowLabels="false" ShowBarPointers="false"&gt;

&lt;Position X="54" Y="50" /&gt;

&lt;Border Color="#C0B08E" Width="1" /&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img1.png)
{:.image }


## Adding scale collection

Scale is the basic element of Linear Gauge. Scale collection is directly added to the gauge object. Refer the following code example to add scale collection in Gauge control. 



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false"&gt;

&lt;%--For Adding scale collection -- %&gt;

&lt;Scales&gt;

&lt;ej:Scales width="8" BackgroundColor="grey" ShowMarkerPointers="true" ShowBarPointers="false"&gt;

&lt;Position X="20" Y="50" /&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;%-- For Adding Marker Pointer Collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers type="Pentagon" Placement="Near" Length="10" Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282"&gt;                         &lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick Collection -- %&gt;



&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="50" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img2.png)
{:.image }


## Scale Customization

Colors and Border

* The Scale border is modified with border object. It has two border property, color and width  are used to customize the border color of the scale and border width of the scale. Setting the background color improves the look and feel of the Linear Gauge. You can customize the background color of the scale using backgroundColor. 
* Scales are used to enable or disable various properties such as showRanges, showIndicators, showCustomLabels, showLabels, showTicks, showBarPointers and showMarkerPointers. Enable/disable is done by setting the property into two states either “true” or “false”. You can adjust the Opacity of the scale with opacity property.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false"&gt;

&lt;%-- For Adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;%-- Setting scaleopacity and shadowoffset -- %&gt;

&lt;ej:Scales width="8" BackgroundColor="#FE8282" ShowMarkerPointers="true" ShowBarPointers="false" ScaleOpacity="0.5" ShadowOffset="10" Type="RoundedRectangle"&gt;

&lt;Position X="20" Y="50" /&gt;

&lt;%-- For setting scale border color and width -- %&gt;

&lt;Border Color="red" Width="1" /&gt;

&lt;%-- For Adding Marker Pointer Collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#C9E1E5"&gt; &lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick Collection-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding Label collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="50" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img3.png)
{:.image }


## Appearance

* You can improve the appearance of Linear Gauge using various properties. You can set the interval values for the scale with major interval value and minor interval value properties and maximum and minimum value by minimum and maximum property. The width property is used to set the scale bar width. 
* You can also adjust the Opacity of the scale with opacity property. The value for opacity lies between 0 and 1.Linear Gauge contains two scale directions, clockwise and counter clockwise. It can be set with direction property.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false"&gt;

&lt;%-- For Adding Scale Collection-- %&gt;

&lt;%-- Setting Minimum and Maximum value, scale width, Minorinterval and Major interval value-- %&gt; 

&lt;Scales&gt;

&lt;ej:Scales width="18" Minimum="10" Maximum="210" MinorIntervalValue="25" MajorIntervalValue="50" BackgroundColor="Grey" ShowMarkerPointers="true" ShowBarPointers="false"&gt;

&lt;Position X="20" Y="50" /&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;%--Setting Marker Pointer Collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282"&gt; &lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%--Setting Tick Collection-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="30" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%--Setting Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="50" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img4.png)
{:.image }


## Scale Types

Scale Type is an element which decides the appearance of the gauge. Linear Gauge contains three scale types such as,

* Rectangle
* Rounded Rectangle
* Thermometer

Rectangle

For rectangular scale type, the scale renders with rectangular structure. Refer the following code example. 



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent"&gt;

&lt;%-- For Adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;%-- For setting Scale type as rectangle-- %&gt;



&lt;ej:Scales type="rectangle" width="18" Length="300" BackgroundColor="#C0B08E" ShowBarPointers="false" ShowMarkerPointers="false" &gt;

&lt;Position X="54" Y="50" /&gt;

&lt;Border Color="#C0B08E" Width="1"&gt;&lt;/Border&gt;

&lt;%-- For adding barpointer Collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For adding Tick Collection-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img5.png)
{:.image }


Rounded Rectangle

For rounded rectangular scale type, the scale renders as rectangular structure but with constant radius rounded corner. Refer the following code example.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;%-- Adding Scales -- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent"&gt;

&lt;Scales&gt;

&lt;%-- Setting scale type as rounded rectangle-- %&gt;

&lt;ej:Scales type="RoundedRectangle" Direction="Clockwise" width="8" Length="300" BackgroundColor="#206BA4" &gt;

&lt;Position X="60" Y="50" /&gt;

&lt;Border Color="#206BA4" Width="1"&gt;&lt;/Border&gt;

&lt;%-- Adding Bar Pointer Collection-- %&gt;



&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- Adding Ticks-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- Adding Labels-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-20" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- Adding Frame-- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Scales_images/Scales_img6.png)
{:.image }


Thermometer

For thermometer scale type, the scale renders as thermometer structure with rounded bottom. Refer the following code example.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent"&gt;

&lt;Scales&gt;

&lt;%-- Adding Scale Type as Thermometer-- %&gt;

&lt;ej:Scales type="thermometer"  width="18" Length="300" BackgroundColor="#C0B08E" ShowBarPointers="false" ShowMarkerPointers="false"&gt;

&lt;Position X="54" Y="50" /&gt;

&lt;Border Color="#C0B08E" Width="1"&gt;&lt;/Border&gt;

&lt;%-- For setting bar pointers-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For setting Ticks-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far"&gt;

&lt;DistanceFromScale X="-27" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For setting labels-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-20" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



![](Scales_images/Scales_img7.png)
{:.image }
Execute the above code to render the following output.



















_Linear Gauge with scale type as Thermometer_

