---
layout: post
title: Bar Pointers | LinearGauge | ASP.NET Webforms | Syncfusion
description: bar pointers
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Bar Pointers

Bar Pointer value points out the actual value set in the Linear Gauge as marker pointer. You can set the values of the various bar pointer attributes such as value, width, border and color in bar pointer collection.  You can also customize the pointers to improve the appearance of gauge.

## Adding bar pointer collection

You can add Bar Pointer collection directly to the scale object. Refer the following code example.

{% highlight html %}

<%-- Render Linear Gauge-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" value="78" EnableAnimation="false">

<Scales>

<ej:Scales  BackgroundColor="transparent" ShowMarkerPointers="false" ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<%-- For setting bar pointer-- %>

<BarPointerCollection>

<ej:BarPointers Width="5" BarPointerBackgroundColor="grey"></ej:BarPointers>

</BarPointerCollection>

<%-- For setting Ticks-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<%-- For setting Frame object-- %>

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.


![](Bar-Pointers_images/Bar-Pointers_img1.png)



## Adding bar pointer value

Bar pointer value is also important element in the Linear Gauge as it indicates the gauge value. Real purpose of the Linear Gauge is based on the pointer value. You can set the bar pointer value either directly during rendering the control or it can be achieved by public method.


{% highlight html %}

<%-- Render Linear Gauge-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  EnableAnimation="false">

<Scales>

<ej:Scales  BackgroundColor="transparent" ShowMarkerPointers="false" ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<%-- For setting Bar Pointer Collection-- %>

<%-- For setting bar pointer value-- %>

<BarPointerCollection>

<ej:BarPointers Width="5" BarPointerValue="91" BarPointerBackgroundColor="grey"></ej:BarPointers>

</BarPointerCollection>

<%-- For setting Tick Collection-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<%-- For Adding Frame Object-- %>

<Frame InnerWidth="8" OuterWidth="10"                   BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Bar-Pointers_images/Bar-Pointers_img2.png)



## Pointer Styles

Appearance

* Based on the value, the bar pointer points out the label value. You can set the bar pointer width using width property and you can also adjust the opacity of the pointer using opacity property that holds the value between 0 and 1. You can add the gradient effects to the pointer using gradient object. 
* The marker pointer border is modified with the object border. It has two border property, color and width which are used to customize the border color of the scale and border width of the marker pointer. The background color can be customized with attribute backgroundColor.


{% highlight html %}

<%-- Render Linear Gauge-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  EnableAnimation="false">

<Scales>

<ej:Scales  BackgroundColor="transparent" ShowMarkerPointers="false" ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<%-- For setting bar pointer width and opacity -- %>

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerValue="91" BarPointerBackgroundColor="red" BarPointerOpacity="0.7">

<Border Color="#860201" Width="2" />

</ej:BarPointers>

</BarPointerCollection>

<%-- For Adding Tick Collection-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<%-- For Adding Frame Object-- %>

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.



![](Bar-Pointers_images/Bar-Pointers_img3.png)



## Positioning the pointer

* Bar pointer can be positioned with two properties such as distanceFromScale and placement. The distanceFromScale property defines the distance between the scale and pointer element. 
* The placement property is used to locate the pointer with respect to scale either inside or outside the scale or along the scale. It is an enumerable data type.

{% highlight html %}

<%-- For Linear Gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  EnableAnimation="false">

<Scales>

<ej:Scales  BackgroundColor="transparent" ShowMarkerPointers="false" ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<%--Setting bar pointer-- %>

<%--Setting distanceFromScale-- %>

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerValue="91" BarPointerdistanceFromScale="20" BarPointerBackgroundColor="#8BABFF" >

<Border Color="#860201" Width="2" />

</ej:BarPointers>

</BarPointerCollection>

<%-- For setting Tick Collection-- %>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

</ej:Scales>

</Scales>

<%-- For adding frame Object-- %>

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Bar-Pointers_images/Bar-Pointers_img4.png)



## Multiple Bar Pointers

Linear Gauge can contain multiple bar pointers on it. You can use any combination and any number of pointers in a gauge. That is, a Gauge can contain any number of marker pointer and any number of bar pointers. Refer the following code example containing multiple bar pointers.


{% highlight html %}

<%--For Setting Linear gauge-- %>

<ej:LinearGauge runat="server" ID="PointerGauge" height="500" Width="300" LabelColor="grey" EnableAnimation="false">

<Scales>

<ej:Scales  BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true" ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<BarPointerCollection>

<%--Setting bar pointer1-- %>

<ej:BarPointers Width="10" BarPointerValue="91" BarPointerdistanceFromScale="60" BarPointerBackgroundColor="#8BABFF" ></ej:BarPointers>

<%--Setting bar pointer2-- %>

<ej:BarPointers Width="10" BarPointerValue="51" BarPointerdistanceFromScale="20" BarPointerBackgroundColor="#FDB761" ></ej:BarPointers>

<%--Setting bar pointer3-- %>

<%--Setting bar pointer width, pointer value, backgroundcolor and distancefrom scale-- %>

<ej:BarPointers Width="10" BarPointerValue="88" BarPointerdistanceFromScale="100" BarPointerBackgroundColor="red" >

</ej:BarPointers>

</BarPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%-- For setting Custom label Collection-- %>

<CustomLabelCollection>

<ej:CustomLabel Value="Mathematics Mark Comparision">

<Position X="55" Y="97" />

</ej:CustomLabel>

<ej:CustomLabel Value="Halfyearly" TextAngle="90">

<Position X="72" Y="87" />

</ej:CustomLabel>

<ej:CustomLabel Value="Quaterly" TextAngle="90">

<Position X="56" Y="87" />

</ej:CustomLabel>

<ej:CustomLabel Value="Annual" TextAngle="90">

<Position X="87" Y="87" />

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

<%-- For adding frame object-- %>

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_dark1.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.



![](Bar-Pointers_images/Bar-Pointers_img5.png)



