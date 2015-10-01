---
layout: post
title: RTL support | Slider | ASP.NET | Syncfusion
description: rtl support
platform: aspnet
control: Slider
documentation: ug
---

# RTL support

Slider includes the Right to Left alignment support. Operations in the Slider are performed from Right to Left.

## Enabling RTL 

Use the EnableRTL property to enable the RTL support. By default this property is disabled. Data type of this property is Boolean.

In an ASPX page, define the Slider control and set the EnableRTL property to true. 

{% highlight html %}

<ej:Slider ID="RangeSlider" runat="server" Width="500" Values="25,75" SliderType="Range" EnableRTL="true"></ej:Slider>

{% endhighlight %}



The following screenshot displays the output of the above code example.

 ![](RTL-support_images/RTL-support_img1.png)



