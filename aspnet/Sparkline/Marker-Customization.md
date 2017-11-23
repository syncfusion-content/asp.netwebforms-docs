---
layout: post
title: Markers Customization
description: Learn how to add markers to Sparkline.
platform: aspnet
control: Sparkline
documentation: ug
---

## Marker Customization

You can customize markers by initializing the `MarkerSettings` property. The customization options allow you to change the `Visibility`, `Fill`, `Width`, `Opacity`and `Border` options `Color`, `Width`, `Opacity` for marker. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}
 
<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server">    
    <MarkerSettings Visible="true" Fill="#ff14ae" Width="4" Border-Width="1"></MarkerSettings>
</ej:Sparkline>

{% endhighlight %}

![](Marker-Customization_images/Marker-Customization_img1.png)
