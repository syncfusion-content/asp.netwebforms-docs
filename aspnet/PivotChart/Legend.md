---
layout: post
title: Legend | PivotChart | ASP.NET | Syncfusion
description: legend
platform: aspnet
control: PivotChart
documentation: ug
---

#Legend

##Legend Visibility

You can enable or disable legend using the `Visible` property inside the `Legend` object.

N> By default, the legend is visible in PivotChart.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Legend Visibility
    <Legend Visible="true" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img1.png) 

##Legend Shape

You can customize the legend `Shape` in PivotChart control. Default value of legend shape is “rectangle”. Following legend shapes that are supported:
* rectangle
* circle
* cross
* diamond
* pentagon
* hexagon
* star
* ellipse
* triangle etc.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Applying legend shape
    <Legend Visible="true" RowCount="3" Shape="star" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img2.png) 

##Legend Position
By using the `Position` property, you can place the legend at top, bottom, left or right of the PivotChart. 

N> Default value of legend position is "bottom" in PivotChart.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Place the legend at top of the Chart
    <Legend Visible="true" RowCount="3" Position="top" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img3.png) 

##Legend Title
To add the legend title, you have to specify the title text in `Title.text` property.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Place the legend at top of the Chart
    <Legend Visible="true">
        <Title text="Countries"></Title>
    </Legend>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img4.png) 

##Legend Alignment
You can align the legend to center, far and near based on its position in the Chart area using the `Alignment` option.
 
{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Aligning the legend near to the Chart
    <Legend Visible="true" RowCount="3" Alignment="near" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img5.png)

##Legend Items - Size and Border
By using the legend `ItemStyle.Width`, `ItemStyle.Height` and `ItemStyle.Border` properties, you can change the legend items - size and border.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Changing legend items border, height and width
    <Legend Visible="true" ItemStyle-Width="12" ItemStyle-Height="12" ItemStyle-Border-Color="Magenta" ItemStyle-Border-Width="1.5"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img6.png)
 
##Legend Border
By using the `Border` option in legend, you can customize border color and width.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    //Setting border color and width to legend
    <Legend Visible="true" Border-Width="2" Border-Color="#FFC342" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img7.png)

##Legend Text
By using the `Font` option, you can customize the font family, font style, font weight and size of the legend text. 

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
    <Legend>
        //Customizing the legend text
        <Font FontFamily="SegoeUI" FontSize="13px" FontStyle="italic" FontWeight="Bold">
       </Font>
    </Legend>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](Legend_images/Legend_img8.png)