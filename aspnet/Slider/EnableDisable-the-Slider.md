---
layout: post
title: Enable or Disable in ASP.NET Slider | Syncfusion
description: Learn here all about enable or disable slider support in Syncfusion ASP.NET Slider control,its element, and more
platform: aspnet
control: Slider
documentation: ug
---

# Enable or Disable in ASP.NET Slider

Slider control includes an option to enable/disable it. When you disable the Slider, it is displayed in a blur state and you cannot perform any operations in it.

## Enabled     

By using this Enabled property, you can enable/disable the Slider. Data type of this property is Boolean. Also you can enable/disable the **Slider** by using [enable](https://help.syncfusion.com/api/js/ejslider#methods:enable) and [disable](https://help.syncfusion.com/api/js/ejslider#methods:disable) methods.

In an ASPX page, define the Slider control and set the Enabled property to false to disable the Slider. 

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Width="500" Value="60" Enabled="false"> </ej:Slider>

{% endhighlight %}

The following screenshot displays the output of the above code example.

 ![Enable in ASP.NET Slider](EnableDisable-the-Slider_images/EnableDisable-the-Slider_img1.png)



