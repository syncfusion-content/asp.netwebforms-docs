---
layout: post
title: Multiple Items | DigitalGauge | ASP.NET Webforms | Syncfusion
description: multiple items 
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Multiple Items 

The text in the Digital Gauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and y variable positions the text in the vertical axis.





{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="500" Height="300">



<%-- Adding frame background image --%>



<Frame BackgroundImageUrl="../Content/images/gauge/Board1.jpg"/>



<Items>



<%-- Adding Item 1 --%>



<ej:DigitalGaugeItems Value="YELLOW">



<Position X="80" Y="0"/>



<SegmentSettings Color="Yellow"/>



</ej:DigitalGaugeItems>



<%-- Adding Item 1 --%>



<ej:DigitalGaugeItems Value="RED">



<Position X="80" Y="20"/>



<SegmentSettings Color="Red"/>



</ej:DigitalGaugeItems>



<%-- Adding Item 1 --%>



<ej:DigitalGaugeItems Value="GREEN">



<Position X="80" Y="40"/>



<SegmentSettings Color="Green"/>



</ej:DigitalGaugeItems>



</Items>



</ej:DigitalGauge>


{% endhighlight %}


Execute the above code example to render the DigitalGauge as follows.



![](Multiple-Items_images/Multiple-Items_img1.png)


Digital Gauge control with multiple items
{:.caption} 


