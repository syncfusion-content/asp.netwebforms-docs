---
layout: post
title: Maximum and Minimum length | Captcha | ASP.NET Webforms | Syncfusion
description: maximum and minimum length
platform: aspnet
control: Captcha
documentation: ug
---

# Maximum and Minimum length

You can limit the Captcha characters by MinimumLength and MaximumLength properties. MaximumLength property is used to define the maximum number of characters to be displayed in the image. MinimumLength sets minimum number of captcha characters required to display.

In the ASPX page, include the following Captcha control code example with minimum and maximum length supports.


{% highlight html %}

<ej:Captcha ID="captcha" MaximumLength="6" MinimumLength="5" runat="server"></ej:Captcha>

{% endhighlight %}



The following screenshot illustrates the Captcha with Minimum and Maximum length support. 

![](Maximum-and-Minimum-length_images/Maximum-and-Minimum-length_img1.png)



