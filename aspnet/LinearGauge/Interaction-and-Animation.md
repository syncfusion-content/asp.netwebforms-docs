---
layout: post
title: Interaction-and-Animation
description: interaction and animation
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Interaction and Animation

* Linear Gauge control contains Interaction feature. You can use this interaction feature to change the pointer values manually either by clicking or dragging the pointer over the Gauge. It dynamically changes the value of pointer when dragged. To Enable/Disable the user interaction you can use the readOnly Boolean property. The user interaction option is enabled when you set readOnly property as false. By default it holds the true value.
* Linear Gauge contains another attractive concept called Animation. The animation option enables the movement of the pointer from the minimum value to the current value. You can use animation option to change the pointer value dynamically. You can enable/ disable it using enableAnimation property. To enable animationset enableAnimation to ‘true’. 
* By default it holds the true value. You can control the speed of the pointer during animating using animationSpeed. It is a numerical value that holds the time in mille seconds. That is when setting value is 1000, it is considered as 1 second.



[ASP]

&lt;%-- For Linear Gauge rendering -- %&gt;

&lt;%-- For enable Animation, Animation speed and user interaction-- %&gt;

&lt;ej:LinearGauge runat="server" Value="78" ID="PointerGauge"  enableAnimation="true" AnimationSpeed="1000" ReadOnly="false"&gt;

&lt;%-- For Adding Scale collection-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;%-- For Adding bar pointer collection-- %&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers BarPointerValue="78" Width="5" BarPointerBackgroundColor="grey"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding Bar pointer Collection-- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers width="10" Length="10"  MarkerBackgroundColor="grey" MarkerdistanceFromScale="-12"&gt;&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For Adding Tick collection-- %&gt;

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

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Interaction-and-Animation_images/Interaction-and-Animation_img1.png)
{:.image }


