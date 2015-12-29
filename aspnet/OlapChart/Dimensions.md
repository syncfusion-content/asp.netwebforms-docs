---
layout: post
title: Dimensions
description: dimensions
platform: aspnet
control: OlapChart
documentation: ug
---

#Dimensions

##Set size in percentage

You can customize the OlapChart dimension by setting the width and height of the widget in percentage.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Set size to Chart container
    <Size Width="80%" Height="80%"></Size>
</ej:OlapChart>

{% endhighlight %}

##Set size in pixels

You can customize the OlapChart dimension by setting the width and height of the widget in pixels.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"  ClientIDMode="Static">
    //Set size to Chart container
    <Size Width="950px" Height="460px"></Size>
 </ej:OlapChart>

{% endhighlight %}
 
![](Dimensions_images/Dimensions.png) 

##Responsive

OlapChart widget supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in OlapChart by setting `IsResponsive` property to true.

{% highlight html %}

//Enable responsiveness to change the Chart size dynamically.
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"  ClientIDMode="Static" IsResponsive="true">
    <Size Width="950px" Height="460px"></Size>
 </ej:OlapChart>

{% endhighlight %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

