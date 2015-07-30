---
layout: post
title: Basic-Settings
description: basic settings
platform: common
control: Linear Gauge
documentation: ug
---

# Basic Settings

## Adding Dimension

* The basic customization for any control is setting the dimension. Here dimension refers the two major attributes, height and width. The height and width assigned in the control will render the canvas element in the given size. 
* The value attribute is used to set all pointer value in the Linear Gauge control. The attributes, minimum and maximum value are used to set the minimum value and maximum value for all the scales exist in the Linear Gauge control.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;%-- For setting Width, height and pointer value-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="78" Width="300" Height="500" &gt;

&lt;Scales&gt;

&lt;%-- For setting Minimum and Maximum value-- %&gt;

&lt;%-- Adding scale collection-- %&gt;

&lt;ej:Scales  Minimum="10" Maximum="110" BackgroundColor="transparent" ShowBarPointers="true" ShowMarkerPointers="false"&gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;%--Adding barpointer collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- Adding Tick Collection-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img1.png)
{:.image }


## Adding frame

* Frame is the element that decides the appearance of the Linear Gauge. You can customize it by using the object called frame. It contains frame inner width, frame outer width and frame background image URL properties. 
* The innerWidth of the frame defines the distance between the canvas element and the frame and the outerWidth refers to distance from the frame. backgroundUrl is used to set the background image for the frame.



[ASP]



&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" EnableAnimation="false" &gt;

&lt;Scales&gt;

&lt;ej:Scales  BackgroundColor="transparent" ShowBarPointers="true" ShowMarkerPointers="false"&gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers BarPointerValue="78" Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- setting Frame -- %&gt;



&lt;%-- For setting Frame innerwidth, outerwidth and background Image Url-- %&gt;

&lt;Frame InnerWidth="8" OuterWidth="10" BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output. 

![C:/Users/giftline.jebamani/Desktop/a.png](Basic-Settings_images/Basic-Settings_img2.png)
{:.image }


## Appearance

* The attribute orientation is used to render the Linear Gauges either in horizontal position or vertical position.You can set the background color for the Linear Gauge for better appearance using the backgroundColor property. borderColor specifies the border color of the Linear Gauge. You can also add gradient effects to Linear Gauge with the help of pointerGradient1 and pointerGradient2 attribute.
* Theme is the basic property of any control. It is used to set the theme for Linear Gauge. There are two types of themes used for Linear Gauge such as
* flatlight
* flatdark



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;%-- For setting theme, orientation, labelcolor-- %&gt;

&lt;ej:LinearGauge runat="server" Orientation="Horizontal" LabelColor="black" ID="PointerGauge" Value="78" Width="400" Height="100" enableAnimation="false" Themes="flatLight" BackgroundColor="transparent"&gt;

&lt;%-- For Adding Scales-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales direction="Clockwise"  BackgroundColor="transparent" ShowBarPointers="true" ShowMarkerPointers="false" &gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;%-- For Adding Bar Pointers-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding Ticks-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="0" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="0" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding label pointers-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="5" Y="-5" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;





Execute the above code to render the following output.

![](Basic-Settings_images/Basic-Settings_img3.png)
{:.image }


## Responsive 

* For any display devices, the control is to be rendered based on the space in that device. The control must be responsive. For this purpose resizing property is present in Linear Gauge control. 
* The Linear Gauge renders with the specified value. When the browser changes its size, the canvas element checks the dimension with its parent element and if there are any changes in parent dimension, gauge control also changes the dimension based on its parent changes. You can enable this feature using enableResize property.



[ASP]

&lt;%-- For Linear Gauge rendering-- %&gt;

&lt;%-- For enabling responsible layout-- %&gt;

&lt;ej:LinearGauge runat="server" Orientation="Horizontal" LabelColor="black" EnableResize="true" ID="PointerGauge" Value="78" Width="400" Height="100" enableAnimation="false" Themes="flatLight" BackgroundColor="transparent"&gt;

&lt;%-- For Adding Scale collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales direction="Clockwise"  BackgroundColor="transparent" ShowBarPointers="true" ShowMarkerPointers="false" &gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;%-- For Adding bar pointer collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding tick collection-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="0" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c"&gt;

&lt;DistanceFromScale X="0" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For Adding label collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels Angle="90"&gt;

&lt;DistanceFromScale X="5" Y="-5" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For Adding Frame-- %&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Basic-Settings_images/Basic-Settings_img4.png)
{:.image }


