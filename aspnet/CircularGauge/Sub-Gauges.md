---
layout: post
title: Sub-Gauges
description: sub gauges
platform: aspnet
control: Circular Gauge
documentation: ug
---

# Sub Gauges

A Circular Gauge containing another circular gauge is said to be Sub Gauges. Inorder to make  a sample like watch that has second gauge, minute gauge and hour gauge, sub gauges are used.

## Adding Sub Gauges

Sub gauge collection is directly added to the scale object. Refer the following code example to add custom sub gauge collection in a Gauge control

{% highlight html %}

[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;%--For setting sub gauge -- %&gt;

&lt;ej:CircularGauge  runat="server" ID="Subgauge1" value="50" BackgroundColor="blue"  Radius="150"&gt;&lt;/ej:CircularGauge&gt;



&lt;ej:CircularGauge runat="server" Value="50" ID="CircularGauge1"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales radius="190"&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers  Value="0"  length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;labelCollection&gt;

&lt;ej:CircularLabels type="major" /&gt;

&lt;/labelCollection&gt;

&lt;SubGaugeCollection&gt;

&lt;ej:SubGauge ControlID="Subgauge1" Height="200"  Width="200"&gt;

&lt;Position X="100" Y="120"/&gt;

&lt;/ej:SubGauge&gt;

&lt;/SubGaugeCollection&gt;



&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}

### Basic Customization

Basic attributes such as height and width property are used to set height and width of the sub gauge. You can easily position the gauge in another gauge using the position object and by giving the X and Y Coordinates value. controlID attribute is used to specify the sub gauge ID.

{% highlight html %}

[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge  runat="server" ID="Subgauge1" value="50" BackgroundColor="blue" radius="110"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales radius="110"&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;



&lt;/ej:CircularGauge&gt;



&lt;ej:CircularGauge runat="server" ID="CircularGauge1" Height="500" Width="500" Value="50"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales radius="190"&gt;



&lt;SubGaugeCollection&gt;

&lt;%--For enabling animation and setting animation speed-- %&gt;

&lt;ej:SubGauge ControlID="Subgauge1" Height="200"  Width="200"&gt;

&lt;Position X="200" Y="150"/&gt;

&lt;/ej:SubGauge&gt;

&lt;/SubGaugeCollection&gt;



&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}















Execute the above code to render the following output.

 ![](Sub-Gauges_images/Sub-Gauges_img1.png)
{:.image }




### Multiple Sub Gauges

You can set multiple sub gauges in a single Circular Gauge by adding an array of sub gauge objects. Refer the following code example for multiple sub gauges functionality.

{% highlight html %}

[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge  runat="server" ID="Subgauge1"  BackgroundColor="#f5b43f" &gt;

&lt;/ej:CircularGauge&gt;

&lt;ej:CircularGauge  runat="server" ID="Subgauge2"  BackgroundColor="#f5b43f" &gt;

&lt;/ej:CircularGauge&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1" Height="500" Width="500" &gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true"  ShowscaleBar="false" radius="250" Size="5" Maximum="100"&gt;

&lt;SubGaugeCollection&gt;

&lt;%--subgauge1--%&gt;

&lt;ej:SubGauge ControlID="Subgauge1" Height="200"  Width="200"&gt;

&lt;Position X="200" Y="150"/&gt;

&lt;/ej:SubGauge&gt;

&lt;%--subgauge2-- %&gt;

&lt;ej:SubGauge ControlID="Subgauge2" Height="200"  Width="200"&gt;

&lt;Position X="50" Y="200"/&gt;

&lt;/ej:SubGauge&gt;

&lt;/SubGaugeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

{% endhighlight %}

Execute the above code to render the following output.

 ![](Sub-Gauges_images/Sub-Gauges_img2.png)
{:.image }








