---
layout: post
title: Appearance
description: appearance
platform: aspnet
control: OlapChart
documentation: ug
---

#Appearance

##Built-in Themes

Following are the built-in themes available in the OlapChart.

* flatlight
* flatdark
* gradientlight
* gradientdark
* azure
* azuredark
* lime
* limedark
* saffron
* saffrondark
* gradient-azure
* gradient-azuredark
* gradient-lime
* gradient-limedark
* gradient-saffron
* gradient-saffrondark

By using the `Theme` property, you can set the desired theme in OlapChart. By default, **"Flat Light"** theme is applied to OlapChart.

{% highlight html %}

//Using gradient theme
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"  Theme="GradientLight" ClientIDMode="Static">
  <Size Width="950px" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}

![](Appearance_images/themes.png)

##OlapChart - Area Customization

###Border Customization
To customize the OlapChart border, use `Border` property in OlapChart.

{% highlight html %}

//Customize the chart border and opacity
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"  Border-Width="2" Border-Color="#FF0000" ClientIDMode="Static">
<Size Width="950px" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}

![](Appearance_images/bordercustomize.png)

###Background Customization
The OlapChart control background can be customized by using the `Background` property in the Chart area.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Setting background for Chart area
    <ChartArea Background="skyblue"></ChartArea>
    <Size Width="950px" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}

![](Appearance_images/backgroundcutomize.png)

###Grid Bands Customization
By using the `AlternateGridBand` property of the axis, you can provide different color for grid rows and columns formed by the grid lines in the Chart area. The properties `Odd` and `Even` are used to customize the grid bands at odd and even positions respectively.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Customizing horizontal grid bands at even position
    <primaryyaxis>
        <AlternateGridBand Even-Fill="#A7A9AB" Even-Opacity="0.1" />
    </primaryyaxis>
    <Size Width="950px" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}

![](Appearance_images/gridbands.png)

###Animation
You can enable animation by using the `EnableAnimation` property under `CommonSeriesOptions` of the OlapChart control. This animates the Chart series on two occasions - when the Chart is loaded for the first time and when you change the series type by using the `Type` property.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Enabling animation in series
    <CommonSeriesOptions EnableAnimation="True" />
    <Size Width="950px" Height="460px"></Size>
</ej:OlapChart>

{% endhighlight %}   
