---
layout: post
title: Multiple-Items
description: multiple items 
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Multiple Items 

The text in the Digital Gauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and y variable positions the text in the vertical axis.





{% highlight html %}

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="500" Height="300"&gt;



&lt;%-- Adding frame background image --%&gt;



&lt;Frame BackgroundImageUrl="../Content/images/gauge/Board1.jpg"/&gt;



&lt;Items&gt;



&lt;%-- Adding Item 1 --%&gt;



&lt;ej:DigitalGaugeItems Value="YELLOW"&gt;



&lt;Position X="80" Y="0"/&gt;



&lt;SegmentSettings Color="Yellow"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;%-- Adding Item 1 --%&gt;



&lt;ej:DigitalGaugeItems Value="RED"&gt;



&lt;Position X="80" Y="20"/&gt;



&lt;SegmentSettings Color="Red"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;%-- Adding Item 1 --%&gt;



&lt;ej:DigitalGaugeItems Value="GREEN"&gt;



&lt;Position X="80" Y="40"/&gt;



&lt;SegmentSettings Color="Green"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;/Items&gt;



&lt;/ej:DigitalGauge&gt;


{% endhighlight %}


Execute the above code example to render the DigitalGauge as follows.



![](Multiple-Items_images/Multiple-Items_img1.png)
{:.image }




