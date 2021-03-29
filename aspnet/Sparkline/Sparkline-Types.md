---
layout: post
title: Sparkline types
description: What are the different types of Sparkline available in Essential html Chart.
platform: aspnet
control: Sparkline
documentation: ug
---

# Sparkline Types

## Line Type

To render a Line type Sparkline, set the `Type` as **line**. To change the color and width of the line, you can use the `Fill` and `Width` property.	

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" Width="3" Fill="#33ccff" runat="server">          
</ej:Sparkline>

{% endhighlight %}

![ASPNET Sparkline Sparkline-Types Image1](Sparkline-Types_images/Sparkline-Types_img1.png)

## Column Type

To render a Column Sparkline, set the type as **column** To change the color of the column, you can use the `Fill` property.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" Type="Line" Fill="#33ccff" runat="server">          
</ej:Sparkline>

{% endhighlight %}

![ASPNET Sparkline Sparkline-Types Image2](Sparkline-Types_images/Sparkline-Types_img2.png)

## Area Type

To render an Area Sparkline, you can specify the type as **area**. To change the Area color, you can use the `Fill` property

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" Type="Area" Fill="#69D2E7" runat="server">          
</ej:Sparkline>

{% endhighlight %}

![ASPNET Sparkline Sparkline-Types Image3](Sparkline-Types_images/Sparkline-Types_img3.png)

## WinLoss Type

WinLoss Sparkline render as a column segment and it show the positive, negative and neutral values. You can customize the positive and negative color of the win-loss type.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" Type="WinLoss" Fill="#69D2E7" runat="server">          
</ej:Sparkline>

{% endhighlight %}

![ASPNET Sparkline Sparkline-Types Image4](Sparkline-Types_images/Sparkline-Types_img4.png)

## Pie Type

You can create a pie type sparkline by setting the type as **pie**. Colors for the pie can be customize using `Palette` property.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" Type="Pie" runat="server">
</ej:Sparkline>

{% endhighlight %}

{% highlight C# %}

this.Sparkline1.Palette = new List<string>() { "#ff3399", "#33ccff"};

{% endhighlight %}

![ASPNET Sparkline Sparkline-Types Image5](Sparkline-Types_images/Sparkline-Types_img5.png)
