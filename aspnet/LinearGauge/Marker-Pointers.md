---
layout: post
title: Marker-Pointers
description: marker pointers
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Marker Pointers

Marker Pointer value points out the actual value set in the Linear Gauge. You can set values for various pointer attributes such as value, type, length, width, border and color in pointer collection. You can also customize the pointers to improve the appearance of gauge.__

## Adding marker pointer collection

You can add Marker Pointer collection directly to the scale object. To add pointer collection in a gauge control refer the following code example.  


[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false"&gt;

&lt;%-- Adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales  BackgroundColor="transparent" ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;%-- Adding Bar Pointer Collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey" &gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- Adding Marker Pointer Collection -- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" Length="10" MarkerBackgroundColor="grey" MarkerdistanceFromScale="-12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Marker-Pointers_images/Marker-Pointers_img1.png)
{:.image }


## Adding marker pointer value

The value propertyis the important element in the marker pointer collection which indicates the gauge value. Real purpose of the Linear Gauge is based on the pointer value. You can set the pointer value either directly during rendering the control or it can be achieved by public method.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="600" height="150" EnableAnimation="false" Orientation="Horizontal" LabelColor="black" EnableResize="true"&gt;

&lt;%-- Adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales  Direction="Clockwise" Type="RoundedRectangle" BackgroundColor="#AEC75F" ShowBarPointers="true"&gt;

&lt;Border Color="#AEC75F" Width="30" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey" &gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- Adding Marker Pointer Collection-- %&gt;



&lt;%-- For setting marker pointer value-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="30" Value="67.5" MarkerBackgroundColor="#FE5C09" MarkerdistanceFromScale="20" Placement="near"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick Collection-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="100" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For Adding Frame Collection -- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Marker-Pointers_images/Marker-Pointers_img2.png)
{:.image }


## Pointer Styles

Appearance

* Based on the value, thepointer points out the label value. You can set the pointer length and width using length and width property respectively. You can also adjust the opacity of the pointer using the opacity property which holds the value between 0 and 1. You can add the gradient effects to the pointer using gradient object. 
* The marker pointer border is modified with the border object. It contains two border property namely color and width which are used to customize the border color of the scale and border width of the marker pointer. The background color can be customized with attribute backgroundColor.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="600" height="150" EnableAnimation="false" Orientation="Horizontal" LabelColor="black" EnableResize="true"&gt;

&lt;Scales&gt;

&lt;ej:Scales  Direction="Clockwise" Type="RoundedRectangle" BackgroundColor="#AEC75F" ShowBarPointers="true"&gt;

&lt;Border Color="#AEC75F" Width="30" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey" &gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For setting Marker pointer length, width, opacity value and background Color-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="30" Value="67.5" MarkerBackgroundColor="#FCDD34" MarkerdistanceFromScale="20" Placement="near" MarkerOpacity="0.4"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick Collection-- %&gt;



&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="100" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For Adding Frame Object-- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.



![](Marker-Pointers_images/Marker-Pointers_img3.png)
{:.image }


## Positioning the pointer

* You can position the Pointer with two properties, distanceFromScale and placement. The distanceFromScale property defines the distance between the scale and pointer. 
* The Placement property is used to locate the pointer with respect to scale either inside or outside the scale or along the scale. It is an enumerable data type.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="600" height="150" EnableAnimation="false" Orientation="Horizontal" LabelColor="black" EnableResize="true"&gt;

&lt;%-- For Adding Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales  Direction="Clockwise" Type="RoundedRectangle" BackgroundColor="#AEC75F" ShowBarPointers="true"&gt;

&lt;Border Color="#AEC75F" Width="30" /&gt;

&lt;%-- For Adding Bar Pointer Collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey" &gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding Marker Pointer Collection-- %&gt;

&lt;%-- For setting marker pointer placement and distance from scale-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="30" Value="55.5" MarkerBackgroundColor="#01A357" MarkerdistanceFromScale="60" Placement="near" MarkerOpacity="0.4"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick Collection-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="-1" Y="45" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="100" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For Adding Frame Object-- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Marker-Pointers_images/Marker-Pointers_img4.png)
{:.image }


## Types

It is possible to change the dimension of the marker pointer. Dimensions available for marker pointer are,

* Rectangle
* Triangle
* Ellipse
* Diamond
* Pentagon
* Circle
* Slider
* Pointer
* Wedge
* Trapezoid
* Rounded Rectangle



Multiple Marker Pointers

Linear Gauge can contain multiple pointers on it. You can use any combination and any number of pointers in a gauge. That is, a gauge can contain any number of marker pointer and any number of bar pointers. Refer the following code example containing multiple marker pointers.



[ASP]

&lt;%-- Render Linear Gauge-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="600" height="250" EnableAnimation="false" Orientation="Horizontal" LabelColor="black" EnableResize="true" Themes="FlatLight"&gt;

&lt;%-- For setting Scale Collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales  Direction="Clockwise" Type="RoundedRectangle" BackgroundColor="#AEC75F" ShowCustomLabels="true" ShowBarPointers="true"&gt;

&lt;Border Color="#AEC75F" Width="30" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey" &gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For setting marker pointer1 -- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="30" Value="32.2" MarkerBackgroundColor="#01A357" MarkerdistanceFromScale="60" Placement="near"&gt;&lt;/ej:MarkerPointers&gt;

&lt;%-- For setting marker pointer2 -- %&gt;

&lt;ej:MarkerPointers Width="3" Value="23.7" MarkerBackgroundColor="#90DAFB" Type="circle" MarkerdistanceFromScale="60" Placement="near"&gt;&lt;/ej:MarkerPointers&gt;

&lt;%-- For setting marker pointer3-- %&gt;

&lt;ej:MarkerPointers Width="3" Value="23.7" MarkerBackgroundColor="#90DAFB" Type="star" MarkerdistanceFromScale="60" Placement="near"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For setting Tick Collection-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="45" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="45" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="100" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%-- For setting Custom Label Collection-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CustomLabel Value="Weather Condition in California"&gt;

&lt;Position X="49" Y="20" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;





Execute the above code to render the following output.



![](Marker-Pointers_images/Marker-Pointers_img5.png)
{:.image }


