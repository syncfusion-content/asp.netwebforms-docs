---
layout: post
title: Exporting the Digital Gauge | DigitalGauge | ASP.NET Webforms | Syncfusion
description: exporting the digital gauge
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Exporting the Digital Gauge

Digital Gauge has an exporting feature where Gauge control is converted into image format and then exported to client-side. The method API exportImage exports the Digital Gauge. It has two arguments such as filename and file format. For exporting, you can refer the following code example.


{% highlight html %}

<%-- Adding Digital Gauge control --%>

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Value="Syncfusion">



</ej:DigitalGauge>

<script>

$("# DigitalGauge1").ejDigitalGauge("exportImage", "Digital", "PNG");

<script/>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.



![](Exporting-the-Digital-Gauge_images/Exporting-the-Digital-Gauge_img1.png)

Digital Gauge control with Export functionality
{:.caption} 

