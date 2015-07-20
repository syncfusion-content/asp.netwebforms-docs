---
layout: post
title: Ranges-and-Frames
description:  ranges and frames
platform: aspnet
control: Circular Gauge
documentation: ug
---

#  Ranges and Frames

Ranges are used to specify or group the scale values. By using ranges, you can describe the values in the pointers. 

## Adding Range Collection

Range collection is directly added to the scale object. Refer the following code example to add range collection in a Gauge control. 



{% highlight html %}



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"&gt;

&lt;RangeCollection&gt;

&lt;ej:CircularRanges StartValue="20" EndValue="80" BackgroundColor="green" Placement="far"&gt;

&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}

### Range Customization

### Appearance

* The API size is used to specify the width of the ranges.  The major attributes for ranges are startValue and endValue. startValue defines the start position of the ranges and endValue defines the end position of the ranges.
* StartWidth and endWidth are used to specify the range width at the starting and ending position of the ranges. You can add the gradient effects to the ranges by using gradient object.



{% highlight html %}



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"  ShowscaleBar="true" radius="150" Size="5"&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers  Value="0"  length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;labelCollection&gt;

&lt;ej:CircularLabels type="major" /&gt;

&lt;/labelCollection&gt;

&lt;RangeCollection&gt;

&lt;ej:CircularRanges StartValue="20" endValue="80" BackgroundColor="green" Placement="far"&gt;

&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;


{% endhighlight %}


Execute the above code to render the following output.

 ![](Ranges-and-Frames_images/Ranges-and-Frames_img1.png)
{:.image }


### Colors and Border

* By customizing the ranges, the appearance of the Gauge can be improved. The range border is modified with the object called border. It has two border property such as color and width. These are used to customize the border color of the ranges and border width of the ranges. 
* You can set the background color to improve the look and feel of the Circular Gauge. For customizing the background color of the ranges, backgroundColor is used.









{% highlight html %}

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"  ShowscaleBar="true" radius="150" Size="2"&gt;

&lt;%--For setting range start value, end value, background color and border color-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:CircularRanges StartValue="20" endValue="80" BackgroundColor="yellow" Placement="far"&gt;

&lt;Border Color="green" Width="2" /&gt;

&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}

Execute the above code to render the following output.

 ![](Ranges-and-Frames_images/Ranges-and-Frames_img2.png)
{:.image }






### Position the ranges

* You can position ranges using two properties such as distanceFromScale and placement. 
* distanceFromScale property defines the distance between the scale and range. 
* Placement property is used to locate the pointer with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



{% highlight html %}



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"  ShowscaleBar="true" radius="150" Size="2"&gt;

&lt;%--For setting range start value, end value, distance between scale and ranges-- %&gt; 

&lt;RangeCollection&gt;

&lt;ej:CircularRanges StartValue="0" endValue="100" BackgroundColor="green" Placement="far" DistanceFromScale="-30"&gt;

&lt;Border width="2" Color="black" /&gt;

&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}

Execute the above code to render the following output.



 ![](Ranges-and-Frames_images/Ranges-and-Frames_img3.png) 
{:.image }




### Multiple Ranges

You can set multiple ranges by adding an array of ranges objects. Refer the following code example for multiple ranges functionality.



{% highlight html %}



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"  ShowscaleBar="true" radius="150" Size="2" Maximum="100"&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers  Value="40" showbackneedle="true" length="100"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;RangeCollection&gt;

&lt;%--For setting range1-- %&gt;

&lt;ej:CircularRanges StartValue="0" endValue="50" BackgroundColor="green" Placement="far" DistanceFromScale="-30"&gt;&lt;/ej:CircularRanges&gt;

&lt;%--For setting range2 -- %&gt;

&lt;ej:CircularRanges StartValue="50" endValue="80" BackgroundColor="yellow" Placement="far" DistanceFromScale="-30"&gt; &lt;/ej:CircularRanges&gt;

&lt;%--For setting range3--%&gt;

&lt;ej:CircularRanges StartValue="80" endValue="100" BackgroundColor="red" Placement="far" DistanceFromScale="-30"&gt;&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}



Execute the above code to render the following output.

 ![](Ranges-and-Frames_images/Ranges-and-Frames_img4.png)
{:.image }






### Frames

* Frame is the element that decides the appearance of the Circular Gauge. You can customize it using the object called frame.  It has the properties such as frameType, backGroundUrl, halfCircleFrameStartAngle and halfCircleFrameEndAngle.
* frameType is used to specify whether frame is a half circle frame or full circle frame. halfCircleFrameStartAngle and halfCircleFrameEndAngle are used to specify the angle for Gauge with frame type as half circle. backgroundUrl is used to set the background image for the frame.









{% highlight html %}



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1" backgroundColor="#FFCCCC"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales startAngle="180" SweepAngle="180"&gt;

&lt;PointerCap Radius="8" /&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers  type="Needle" needleType="Rectangle" Value="40" width="1" length="120"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;%--For setting halfcircle frame start angle and end angle-- %&gt;

&lt;Frame FrameType="HalfCircle" HalfCircleFrameStartAngle="205" HalfCircleFrameEndAngle="335" /&gt;

&lt;/ej:CircularGauge&gt;


{% endhighlight %}


Execute the above code to render the following output.

 ![](Ranges-and-Frames_images/Ranges-and-Frames_img5.png)
{:.image }














