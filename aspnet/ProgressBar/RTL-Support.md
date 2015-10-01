---
layout: post
title: RTL Support | ProgressBar | ASP.NET | Syncfusion
description: rtl support
platform: aspnet
control: ProgressBar
documentation: ug
---

# RTL Support

Right-to-Left starts from the right side of the page and continues to the left. By default, this option is set to false in the 
ProgressBar control. The EnableRTL option allows the ProgressBar control to display it in the right to left direction.

Add the following code example to the corresponding ASPX page to render ProgressBar control.

{% highlight html %}

<ej:ProgressBar ID="progressbar" runat="server" Value="70" Text="70 %" Height="20" Width="500" EnableRTL="true">
 
</ej:ProgressBar>

{% endhighlight %}

The following screenshot displays the ProgressBar set from Right-to-Left.               
![](RTL-Support_images/RTL-Support_img1.png)
