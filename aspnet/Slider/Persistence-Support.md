---
layout: post
title: Persistence Support | Slider | ASP.NET | Syncfusion
description: persistence support
platform: aspnet
control: Slider
documentation: ug
---

# Persistence Support

This feature supports you to save current model value to browser cookies for state maintenance. When you refresh the web page, the Slider control retains the model value applied from browser cookies. The data type of the EnablePersistence is Boolean.

In an ASPX page, define the Slider control and set the EnablePersistence property to true. 

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Height="20" Width="500" EnablePersistence="true"></ej:Slider>

{% endhighlight %}



