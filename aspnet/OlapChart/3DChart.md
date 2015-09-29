---
layout: post
title: 3D
description: 3d
platform: aspnet
control: OLAP Chart
documentation: ug
---

# 3D

The OlapChart control provides three dimensional view for Bar, Column, StackingBar, StackingColumn and Pie Charts. The representation of data in 3D Chart is very clear and easy to understand when compared to 2D Chart. Three dimensions of the series are seen by rotating them. To enable this functionality, we need to set `enable3D` property to "true".

The following code example explains on how to enable 3D in the Olapchart control.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    <CommonSeriesOptions Type="Column" />
    <Size Width="100%" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}

 ![](3DChart_images/3DChart_images1.png)
 
 



