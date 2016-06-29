---
layout: post
title: Title | PivotChart | ASP.NET | Syncfusion
description: title
platform: aspnet
control: PivotChart
documentation: ug
---

#Title

##Title Text

By using the `Title.text` property, you can add the title text for PivotChart.

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" Url="../wcf/RelationalChartService.svc" ClientIDMode="Static">
    //Adding Chart title
    <Title text="PivotChart"></Title>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Title_images/Title_img1.png)

##Title Alignment
By using the `Title.TextAlignment` property, you can align the PivotChart controls title text to center, far or near.

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" Url="../wcf/RelationalChartService.svc"  ClientIDMode="Static">
    //Change title text alignment
    <Title text="PivotChart" TextAlignment="near"></Title>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Title_images/Title_img2.png)

##Title Customization

By using the `Title` property, you can add the title text for X-axis and Y-axis. Also title text can be customized by using the `Text` and `Font` properties. On setting `EnableTrim` to true, title text could be trimmed based on its length.

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" Url="../wcf/RelationalChartService.svc" ClientIDMode="Static">
    //Customizing axis title
    <PrimaryXAxis Title-Text="Fiscal Year" Title-Font-Color="Grey" Title-Font-FontSize="16px" Title-Font-FontFamily="Segoe UI" Title-Font-FontWeight="Bold" >
    </PrimaryXAxis>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Title_images/Title_img3.png) 

