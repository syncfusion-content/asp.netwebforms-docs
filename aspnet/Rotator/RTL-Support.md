---
layout: post
title: RTL Support | Rotator | ASP.NET Webforms | Syncfusion
description: rtl support
platform: aspnet
control: Rotator
documentation: ug
---

# RTL Support

This feature supports changing the left-to-right alignment of the Rotator to right-to-left (RTL). This sets the Rotator to do its actions from right to left. The property EnableRTL sets the Rotator from right to left. The value set to this property is Boolean type.

In an ASPX page, add the following code example and set the EnableRTL property to false.

{% highlight html %}



// Refers to the Local Data section for style and data bound for rotator items.



<ej:Rotator ID="slidercontent" runat="server" SlideWidth="600px" SlideHeight="350px" EnableRTL="false"DataCaptionField="Caption" DataUrlField="Url"></ej:Rotator>



{% endhighlight %}



