---
layout: post
title: Point Customization
description: Learn how to customize points in Sparkline.
platform: aspnet
control: Sparkline
documentation: ug
---

## Point Customization

You can customize points by initializing the point colors. The customization options allow you to differentiate the `First`, `Last`, `Highest`, `Lowest`, and `Negative` points. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server"
    NegativePointColor="Red"
    HighPointColor="Blue"
    LowPointColor="Orange"
    StartPointColor="Green"
    EndPointColor="Green" >
 </ej:Sparkline>

{% endhighlight %}

![](Point-Customization_images/Point-Customization_img1.png)
