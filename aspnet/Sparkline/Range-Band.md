---
layout: post
title: RangeBand
description: Learn how to add Rangeband to Sparkline .
platform: aspnet
control: Sparkline
documentation: ug
---

## Range Band  

The range band feature is used to highlight a particular range along the y-axis using `StartRange` and `EndRange` property. You can also customize the `Color` and `Opacity` of the `RangeBandSettings`. 

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Container" runat="server">
    <RangeBandSettings StartRange="4" EndRange="30" Color="#ff14ae" Opacity="0.4"></RangeBandSettings>
</ej:Sparkline>

{% endhighlight %}

![ASPNET Sparkline Range-Band Image1](Range-Band_images/Range-Band_img1.png)

