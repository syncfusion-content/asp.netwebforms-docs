---
layout: post
title: Scales | LinearGauge | ASP.NET Webforms | Syncfusion
description: Learn about scales support in Syncfusion ASP.NET Webforms Linear Gauge control and more details.
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



### Adding multiple scales

You can set multiple scales for a single Linear Gauge control by using an array of scale objects. Each scale object is independent of each other. Refer the following code example to add multiple scale collection. 

{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false">

<%-- For adding Scale Collection-- %>

<Scales>

<%-- Adding Scale1-- %>

<ej:Scales width="8" BackgroundColor="Grey" ShowMarkerPointers="true" ShowBarPointers="false">

<Position X="15" Y="50" />

<Border Color="grey" Width="1" />

<MarkerPointerCollection>

<ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282"> </ej:MarkerPointers>

</MarkerPointerCollection>



<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

</TickCollection>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="50" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<%-- Adding scale2 -- %>

<Scales>

<ej:Scales width="8" direction="Clockwise" BackgroundColor="#206BA4" ShowMarkerPointers="false" ShowLabels="false" ShowBarPointers="false">

<Position X="90" Y="50" />

<Border Color="#206BA4" Width="1" />

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" placement="Far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far" >

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<%-- Adding scale3-- %>

<Scales>

<ej:Scales width="18" type="Thermometer" length="300" BackgroundColor="#C0B08E" ShowTicks="false" ShowMarkerPointers="false" ShowLabels="false" ShowBarPointers="false">

<Position X="54" Y="50" />

<Border Color="#C0B08E" Width="1" />

</ej:Scales>

</Scales>

<Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/>

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image1](Scales_images/Scales_img1.png)



## Adding scale collection

Scale is the basic element of Linear Gauge. Scale collection is directly added to the gauge object. Refer the following code example to add scale collection in Gauge control. 



{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false">

<%--For Adding scale collection -- %>

<Scales>

<ej:Scales width="8" BackgroundColor="grey" ShowMarkerPointers="true" ShowBarPointers="false">

<Position X="20" Y="50" />

<Border Color="grey" Width="1" />

<%-- For Adding Marker Pointer Collection-- %>

<MarkerPointerCollection>

<ej:MarkerPointers type="Pentagon" Placement="Near" Length="10" Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282">                         </ej:MarkerPointers>

</MarkerPointerCollection>

<%-- For Adding Tick Collection -- %>



<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- For Adding Label Collection-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="50" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/>

</ej:LinearGauge>


{% endhighlight %}




Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image2](Scales_images/Scales_img2.png)



## Scale Customization

### Colors and Border

* The Scale border is modified with border object. It has two border property, color and width  are used to customize the border color of the scale and border width of the scale. Setting the background color improves the look and feel of the Linear Gauge. You can customize the background color of the scale using backgroundColor. 
* Scales are used to enable or disable various properties such as showRanges, showIndicators, showCustomLabels, showLabels, showTicks, showBarPointers and showMarkerPointers. Enable/disable is done by setting the property into two states either “true” or “false”. You can adjust the Opacity of the scale with opacity property.



{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false">

<%-- For Adding Scale Collection-- %>

<Scales>

<%-- Setting scaleopacity and shadowoffset -- %>

<ej:Scales width="8" BackgroundColor="#FE8282" ShowMarkerPointers="true" ShowBarPointers="false" ScaleOpacity="0.5" ShadowOffset="10" Type="RoundedRectangle">

<Position X="20" Y="50" />

<%-- For setting scale border color and width -- %>

<Border Color="red" Width="1" />

<%-- For Adding Marker Pointer Collection-- %>

<MarkerPointerCollection>

<ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#C9E1E5"> </ej:MarkerPointers>

</MarkerPointerCollection>

<%-- For Adding Tick Collection-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- For Adding Label collection-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="50" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/>

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image3](Scales_images/Scales_img3.png)



## Appearance

* You can improve the appearance of Linear Gauge using various properties. You can set the interval values for the scale with major interval value and minor interval value properties and maximum and minimum value by minimum and maximum property. The width property is used to set the scale bar width. 
* You can also adjust the Opacity of the scale with opacity property. The value for opacity lies between 0 and 1.Linear Gauge contains two scale directions, clockwise and counter clockwise. It can be set with direction property.


{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  enableAnimation="false">

<%-- For Adding Scale Collection-- %>

<%-- Setting Minimum and Maximum value, scale width, Minorinterval and Major interval value-- %> 

<Scales>

<ej:Scales width="18" Minimum="10" Maximum="210" MinorIntervalValue="25" MajorIntervalValue="50" BackgroundColor="Grey" ShowMarkerPointers="true" ShowBarPointers="false">

<Position X="20" Y="50" />

<Border Color="grey" Width="1" />

<%--Setting Marker Pointer Collection-- %>

<MarkerPointerCollection>

<ej:MarkerPointers type="Pentagon" Placement="Near" Length="10"  Width="20" MarkerdistanceFromScale="20" MarkerBackgroundColor="#FE8282"> </ej:MarkerPointers>

</MarkerPointerCollection>

<%--Setting Tick Collection-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="30" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%--Setting Label Collection-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="50" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<Frame backgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/>

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image4](Scales_images/Scales_img4.png)



## Scale Types

Scale Type is an element which decides the appearance of the gauge. Linear Gauge contains three scale types such as,

* Rectangle
* Rounded Rectangle
* Thermometer

### Rectangle

For rectangular scale type, the scale renders with rectangular structure. Refer the following code example. 


{% highlight html %}

<%--For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent">

<%-- For Adding Scale Collection-- %>

<Scales>

<%-- For setting Scale type as rectangle-- %>



<ej:Scales type="rectangle" width="18" Length="300" BackgroundColor="#C0B08E" ShowBarPointers="false" ShowMarkerPointers="false" >

<Position X="54" Y="50" />

<Border Color="#C0B08E" Width="1"></Border>

<%-- For adding barpointer Collection-- %>

<BarPointerCollection>

<ej:BarPointers Width="5" BarPointerBackgroundColor="grey"></ej:BarPointers>

</BarPointerCollection>

<%-- For adding Tick Collection-- %>

<TickCollection>

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image5](Scales_images/Scales_img5.png)



### Rounded Rectangle

For rounded rectangular scale type, the scale renders as rectangular structure but with constant radius rounded corner. Refer the following code example.


{% highlight html %}

<%--For Linear Gauge rendering-- %>

<%-- Adding Scales -- %>

<ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent">

<Scales>

<%-- Setting scale type as rounded rectangle-- %>

<ej:Scales type="RoundedRectangle" Direction="Clockwise" width="8" Length="300" BackgroundColor="#206BA4" >

<Position X="60" Y="50" />

<Border Color="#206BA4" Width="1"></Border>

<%-- Adding Bar Pointer Collection-- %>



<BarPointerCollection>

<ej:BarPointers Width="5" BarPointerBackgroundColor="grey"></ej:BarPointers>

</BarPointerCollection>

<%-- Adding Ticks-- %>

<TickCollection>

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- Adding Labels-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-20" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<%-- Adding Frame-- %>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image6](Scales_images/Scales_img6.png)



#### Thermometer

For thermometer scale type, the scale renders as thermometer structure with rounded bottom. Refer the following code example.

{% highlight html %}

<%--For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" enableAnimation="false" BackgroundColor="transparent">

<Scales>

<%-- Adding Scale Type as Thermometer-- %>

<ej:Scales type="thermometer"  width="18" Length="300" BackgroundColor="#C0B08E" ShowBarPointers="false" ShowMarkerPointers="false">

<Position X="54" Y="50" />

<Border Color="#C0B08E" Width="1"></Border>

<%-- For setting bar pointers-- %>

<BarPointerCollection>

<ej:BarPointers Width="5" BarPointerBackgroundColor="grey"></ej:BarPointers>

</BarPointerCollection>

<%-- For setting Ticks-- %>

<TickCollection>

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#206BA4" Placement="far">

<DistanceFromScale X="-27" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- For setting labels-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-20" Y="0" />

</ej:Labels>

</LabelCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}







Execute the above code to render the following output.

![ASPNET LinearGauge Scales Image7](Scales_images/Scales_img7.png)

