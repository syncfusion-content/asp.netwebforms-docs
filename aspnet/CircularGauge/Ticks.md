---
layout: post
title: Ticks
description: ticks
platform: aspnet
control: Circular Gauge
documentation: ug
---

## Ticks

Ticks are used to mark some values on the scale. Based on the tick’s value you can set the labels on the required position.

### Adding Tick Collection 

Tick collection is directly added to the scale object. Refer the following code example to add tick collection in a Gauge control.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales&gt;

&lt;TickCollection&gt;

&lt;ej:CircularTicks Type="major" Color="red" /&gt;

&lt;/TickCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

Execute the above code to render the following output.

{ ![C:/Users/karthigeyan/Desktop/sa.png](Ticks_images/Ticks_img1.png) | markdownify }
{:.image }




### Tick Customization

* Height and width of the ticks can be applied by using the properties height and width. You can customize ticks with the properties such as angle, color, etc. angle attribute is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. Ticks are two types such as major and minor.
* Major type ticks are for major interval values and minor type ticks are for minor interval values.You can position ticks with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and ticks.  Placement property is used to locate the ticks with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales &gt;

&lt;TickCollection&gt;

&lt;%--For setting tick1-- %&gt;

&lt;ej:CircularTicks Type="major" Color="red" placement="Near"  DistanceFromScale="5"/&gt;

&lt;%--For setting tick2-- %&gt;

&lt;ej:CircularTicks Type="minor" Color="yellow" placement="Near" DistanceFromScale="5"/&gt;

&lt;/TickCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;


Execute the above code to render the following output.

{ ![](Ticks_images/Ticks_img2.png) | markdownify }
{:.image }




