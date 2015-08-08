---
layout: post
title: Ranges
description: ranges 
platform: common
control: Linear Gauge
documentation: ug
---

# Ranges 

Ranges are used to specify or group the scale values. You can describe the values in the pointers using ranges. 

## Adding range collection

Range collection can be directly added to the scale object. Refer the following code example to add range collection in a Linear Gauge control. 



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  Height="150" width="600" labelColor="black" Orientation="Horizontal" EnableResize="true" EnableAnimation="false"&gt;

&lt;%-- For setting scale collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Direction="Clockwise" Width="0" Minimum="-20" Maximum="60" BackgroundColor="transparent" ShowRanges="true" ShowBarPointers="false"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;%-- For setting bar pointer collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For setting marker pointer collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="3" Length="30" MarkerBackgroundColor="#FE5C09" Type="Star" MarkerdistanceFromScale="20" Value="55" Placement="near"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="50" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%-- For setting ticks-- %&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="25" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="25" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%--Setting range-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges StartValue="-20" EndValue="60" StartWidth="0" EndWidth="20" RangeBackgroundColor="#FEBE48" Placement="Near" DistanceFromScale="20"&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Ranges_images/Ranges_img1.png)
{:.image }


## Range Customization

Appearance

The major attributes for ranges are startValue and endValue. The startValue defines the start position of the range and endValue defines the end position of the range. The startWidth and endWidth are used to specify the range width at the starting and ending position of the ranges.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  width="500" labelColor="#8c8c8c" &gt;

&lt;Scales&gt;

&lt;ej:Scales  Width="4" Length="310" BackgroundColor="transparent"  ShowRanges="true"  ShowMarkerPointers="false"&gt;

&lt;Position x="50" Y="50" /&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;Font Size="11px" FontFamily="Segoe UI" FontStyle="Bold"&gt;&lt;/Font&gt;

&lt;DistanceFromScale X="-12" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers BarPointerValue="100" Width="4" BarPointerBackgroundColor="#6FAAB0"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="1" Color="#8c8c8c" /&gt;

&lt;/TickCollection&gt;

&lt;%--Setting range start value, endvalue, backgroundcolor, startwidth, end width and distancefromscale-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges DistanceFromScale="6" StartValue="0" EndValue="50" StartWidth="8" EndWidth="8" RangeBackgroundColor="#F6B53F"&gt;&lt;/ej:Ranges&gt;

&lt;ej:Ranges DistanceFromScale="6" StartValue="70" EndValue="100" StartWidth="8" EndWidth="8" RangeBackgroundColor="#E94649"&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;


Execute the above code to render the following output.



![](Ranges_images/Ranges_img2.png)
{:.image }


## Colors and Border

* You can customize the ranges to improve the appearance of the Gauge. The range border is modified with the object called border. It has two border property such as color and width which are used to customize the border color of the ranges and border width of the ranges. 
* You can set the background color to improve the look and feel of the Linear Gauge. For customizing the background color of the ranges, backgroundColor is used.You can add the gradient effects to the ranges by using gradient object.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="500" labelColor="#8c8c8c" Load="LoadGaugeTheme"&gt;

&lt;Scales&gt;

&lt;ej:Scales  Width="4" Length="310" BackgroundColor="transparent"  ShowRanges="true"  ShowMarkerPointers="false"&gt;

&lt;Position x="50" Y="50" /&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;Font Size="11px" FontFamily="Segoe UI" FontStyle="Bold"&gt;&lt;/Font&gt;

&lt;DistanceFromScale X="-12" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="1" Color="#8c8c8c" /&gt;

&lt;/TickCollection&gt;

&lt;%--Setting range backgroundcolor, bordercolor-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges DistanceFromScale="10" StartValue="0" EndValue="50" StartWidth="3" EndWidth="18" RangeBackgroundColor="#F6B53F"&gt;&lt;Border Color="black" /&gt;&lt;/ej:Ranges&gt;

&lt;ej:Ranges DistanceFromScale="10" StartValue="70" EndValue="100" StartWidth="18" EndWidth="3" RangeBackgroundColor="#E94649"&gt;&lt;Border Color="black" /&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Ranges_images/Ranges_img3.png)
{:.image }


## Positioning the ranges

* You can position ranges using two properties such as distanceFromScale and placement. The distanceFromScale property defines the distance between the scale and range. 
* Placement property is used to locate the pointer with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type. 



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" width="500" labelColor="#8c8c8c" Load="LoadGaugeTheme"&gt;

&lt;Scales&gt;

&lt;ej:Scales  Width="4" Length="310" BackgroundColor="transparent"  ShowRanges="true"  ShowMarkerPointers="false"&gt;

&lt;Position x="50" Y="50" /&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;

&lt;Font Size="11px" FontFamily="Segoe UI" FontStyle="Bold"&gt;&lt;/Font&gt;

&lt;DistanceFromScale X="-12" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="1" Color="#8c8c8c" /&gt;

&lt;/TickCollection&gt;

&lt;%--Setting range placement and distancefromscale-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges DistanceFromScale="-30" Placement="near" StartValue="0" EndValue="50" StartWidth="3" EndWidth="18" RangeBackgroundColor="#F6B53F"&gt;&lt;Border Color="black" /&gt;&lt;/ej:Ranges&gt;

&lt;ej:Ranges DistanceFromScale="-30" Placement="near" StartValue="70" EndValue="100" StartWidth="18" EndWidth="3" RangeBackgroundColor="#E94649"&gt;&lt;Border Color="black" /&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Ranges_images/Ranges_img4.png)
{:.image }


## Multiple Ranges

You can set multiple ranges by adding an array of range objects. Refer the following code example for multiple range functionality.





[ASPX]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Height="150" width="600" Orientation="Horizontal" labelColor="black" EnableResize="true" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales  Width="0" Length="310" BackgroundColor="#AEC75F" Direction="Clockwise" Minimum="-20" Maximum="60"  ShowRanges="true" ShowBarPointers="false"&gt;

&lt;Position x="50" Y="50" /&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="3" length="30" MarkerBackgroundColor="#FE5C09" Type="Star" MarkerdistanceFromScale="20" Placement="Near" Value="55"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="0" Y="50" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c"&gt;

&lt;DistanceFromScale x="-1" Y="20" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" Height="6" Color="#8c8c8c"&gt;

&lt;DistanceFromScale x="-1" Y="20" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;RangeCollection&gt;

&lt;%--Setting range1-- %&gt;

&lt;ej:Ranges DistanceFromScale="20" Placement="near" StartValue="-20" EndValue="0" StartWidth="5" EndWidth="10" RangeBackgroundColor="#2788B1"&gt;&lt;Border Color="#2788B1" /&gt;&lt;/ej:Ranges&gt;

&lt;%--Setting range2-- %&gt;

&lt;ej:Ranges DistanceFromScale="20" Placement="near" StartValue="0" EndValue="20" StartWidth="10" EndWidth="15" RangeBackgroundColor="#A5BA28"&gt;&lt;Border Color="#A5BA28" /&gt;&lt;/ej:Ranges&gt;

&lt;%--Setting range3-- %&gt;

&lt;ej:Ranges DistanceFromScale="20" Placement="near" StartValue="20" EndValue="40" StartWidth="15" EndWidth="20" RangeBackgroundColor="#FEBE48"&gt;&lt;Border Color="#FEBE48" /&gt;&lt;/ej:Ranges&gt;

&lt;%--Setting range4-- %&gt;

&lt;ej:Ranges DistanceFromScale="20" Placement="near" StartValue="40" EndValue="60" StartWidth="20" EndWidth="25" RangeBackgroundColor="red"&gt;&lt;Border Color="red" /&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Ranges_images/Ranges_img5.png)
{:.image }


