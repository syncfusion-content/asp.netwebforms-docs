---
layout: post
title: Animation | Slider | ASP.NET | Syncfusion
description: animation
platform: aspnet
control: Slider
documentation: ug
---

# Animation

This feature includes the animation effect for the Slider while moving the Slider handle.

## Enabling Animation

By default, animation is enabled in the Slider. By using the EnableAnimation property, you can enable/disable the animation effects. Data type of this property is “Boolean”.

In an ASPX page, define the Slider control and set the EnableAnimation property to false to disable the animation effect in the Slider. 

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Width="500" Value="60" EnableAnimation="false"></ej:Slider>

{% endhighlight %}



## Customizing Animation speed

Animation speed of the Slider indicates the speed where the Slider handle can be moved. Higher the value specified for this property decreases the rate of speed where the Slider handle can be moved. You can customize the animation speed of the Slider by using the AnimationSpeed property. Default value of this property is 500.

In an ASPX page, define the Slider control and customize the value of AnimationSpeed property. 

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Width="500" Value="60" AnimationSpeed="600"> </ej:Slider>

{% endhighlight %}



