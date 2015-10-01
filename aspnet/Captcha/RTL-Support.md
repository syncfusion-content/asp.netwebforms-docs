---
layout: post
title: RTL Support | Captcha | ASP.NET Webforms | Syncfusion
description: rtl support
platform: aspnet
control: Captcha
documentation: ug
---

# RTL Support

Right to Left alignment of the Captcha can be achieved by enabling EnableRTL property to true. When this property is set to true, refresh image and audio button are displayed in left side of captcha and also auto validation text box characters are entered from right to left. By default, EnableRTL property value is set to false.

In the ASPX page, include the following Captcha control code example for RTL support.



{% highlight html %}

  <ej:Captcha ID="captcha" EnableRTL="true" ShowAudioButton="true" ShowRefreshButton="true" EnableAutoValidation="true" runat="server"></ej:Captcha>

{% endhighlight %}



The following screenshot illustrates the Captcha with RTL support. 

![](RTL-Support_images/RTL-Support_img1.png)



