---
layout: post
title: Ticks
description: ticks
platform: common
control: Linear Gauge
documentation: ug
---

# Ticks

Ticks are used to mark some values on the scale. Based on the tick’s value you can set the labels on the required position.

## Adding tick collection 

Tick collection can be directly added to the scale object. Refer the following code example to add tick collection in a Linear Gauge control.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="5" BackgroundColor="transparent" Type="RoundedRectangle" ShowBarPointers="true"&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;%-- For adding marker pointer collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" Value="60"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For adding bar pointer collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="#95C7E0"&gt;

&lt;/ej:BarPointers&gt;

&lt;ej:BarPointers Width="6" BarPointerBackgroundColor="#EDC1D7" BarPointerdistanceFromScale="-15" BarPointerValue="30" BarPointerOpacity="0.7"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%--Setting Ticks type, width, color and placement-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" Placement="near" &gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" Placement="near" &gt;

&lt;DistanceFromScale X="-12" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-25" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For setting Frame Object-- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Ticks_images/Ticks_img1.png)
{:.image }


## Tick Customization

Appearance

* Height and width of the ticks can be applied by using the properties height and width. You can customize ticks with the properties like angle, color, etc. angle attribute is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. 
* Ticks are two types such as major and minor. The opacity of the labels can be adjusted with the property opacity. The opacity values lies between 0 and 1.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;%-- For Adding scales-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="5" BackgroundColor="transparent" Type="RoundedRectangle" ShowBarPointers="true"&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" Value="60"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="#95C7E0"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding ticks-- %&gt;

&lt;%--Setting tick type, width, height, color and placement-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Height="14" Angle="10" Color="black" Placement="near" &gt;

&lt;DistanceFromScale X="-10" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="10" Opacity="0.5" Color="black" Placement="near" &gt;

&lt;DistanceFromScale X="-10" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-25" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For Adding frame object-- %&gt;

&lt;Frame InnerWidth="8" OuterWidth="10" BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;


Execute the above code to render the following output.

![](Ticks_images/Ticks_img2.png)
{:.image }


## Types

Ticks are two types such as majorInterval and minorInterval. Major type ticks are for major interval values and minor type ticks are for minor interval values.



[ASP]

&lt;%--For Setting Linear gauge-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="5" BackgroundColor="transparent" Type="RoundedRectangle" ShowBarPointers="true"&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;%-- For setting Marker pointer collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" Value="60"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For setting Bar Pointer Collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="#95C7E0"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%--Setting Tick type, width, color and placement-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Height="14" Color="black" Placement="near" &gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval"&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-25" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.



![](Ticks_images/Ticks_img3.png)
{:.image }


## Positioning the ticks

* You can position ticks with the help of two properties such as distanceFromScale and placement. The property distanceFromScale defines the distance between the scale and ticks. 
* Placement property is used to locate the ticks with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" EnableAnimation="false" ReadOnly="false"&gt;

&lt;%-- For adding scale collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="5" BackgroundColor="transparent" Type="RoundedRectangle" ShowBarPointers="true"&gt;

&lt;Border Color="grey" Width="1" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" length="10" Value="60"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="#95C7E0"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%--Setting tick placement-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Height="14" Color="red" Placement="near" &gt;

&lt;DistanceFromScale X="-10" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Color="grey"&gt;

&lt;DistanceFromScale X="-10" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding label collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;DistanceFromScale X="-25" Y="0" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame InnerWidth="8" OuterWidth="10" BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.



![](Ticks_images/Ticks_img4.png)
{:.image }


