---
layout: post
title: EnableDisable-the-Slider
description: enable/disable the slider
platform: aspnet
control: Slider
documentation: ug
---

## Enable/Disable the Slider

Slider control includes an option to enable/disable it. When you disable the Slider, it is displayed in a blur state and you cannot perform any operations in it.

### Enabled     

By using this Enabled property, you can enable/disable the Slider. Data type of this property is Boolean.

In an ASPX page, define the Slider control and set the Enabled property to false to disable the Slider. 

{% highlight html %}



<ej:Slider ID="BasicSlider" runat="server" Width="500" Value="60" Enabled="false"> </ej:Slider>





{% endhighlight %}

The following screenshot displays the output of the above code example.

{ ![](EnableDisable-the-Slider_images/EnableDisable-the-Slider_img1.png) | markdownify }
{:.image }


