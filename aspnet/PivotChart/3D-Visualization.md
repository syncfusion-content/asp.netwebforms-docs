---
layout: post
title: 3D-Visualization
description: 3d visualization
platform: aspnet
control: PivotChart
documentation: ug
---

# 3D Visualization

The PivotChart control allows you to view the data in a 3D view. Following are the chart types that are supported:

* Bar
* Column
* Stacking Bar
* Stocking Column 
* Pie

## 3D Column Chart

3D Column Chart is rendered by specifying the chart type as **“Column”** in the **“CommonSeriesOptions”** enumeration property as well as by setting the `Enable3D` property to **“true”.**

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    //Set chart type as Column to series
    <CommonSeriesOptions Type="Column" />
    <Size Width="100%" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](3D-Visualization_images/column3d.png)

## 3D Bar Chart

3D Bar Chart is rendered by specifying the chart type as **“Bar”** in the **“CommonSeriesOptions”** enumeration property as well as by setting the `Enable3D` property to **“true”.**

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    //Set chart type as Bar to series
    <CommonSeriesOptions Type="Bar" />
    <Size Width="100%" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](3D-Visualization_images/bar3d.png)

## 3D Stacking Bar Chart
3D Stacking Bar Chart is rendered by specifying the chart type as **“Stacking Bar”** in the **“CommonSeriesOptions”** enumeration property as well as by setting the `Enable3D` property to **“true”.**

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    //Set chart type as StackingBar to series
    <CommonSeriesOptions Type="StackingBar" />
    <Size Width="100%" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](3D-Visualization_images/stackingbar3d.png)

## 3D Stacking Column Chart
3D Stacking Column Chart is rendered by specifying the chart type as **“Stacking Column”** in the **“CommonSeriesOptions”** enumeration property as well as by setting the `Enable3D` property to **“true”.**

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    //Set chart type as StackingColumn to series
    <CommonSeriesOptions Type="StackingColumn" />
    <Size Width="100%" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

![](3D-Visualization_images/stackingcolumn3d.png)

## 3D Pie Chart
3D Pie Chart is rendered by specifying the chart type as **"Pie"** in the **"CommonSeriesOptions"** enumeration property as well as by setting the `Enable3D` property to **“true”.**

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" Enable3D="true" Rotation="24" ClientIDMode="Static">
    //Set chart type as pie to series
    <CommonSeriesOptions Type="Pie" />
    <Size Width="100%" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}   

![](3D-Visualization_images/pie3d.png)

##Rotating 3D Chart
We can rotate the 3D Chart towards left or right by setting an appropriate angle value to the `Rotation` property. The direction of the Chart display depends upon the positive or negative angle value.

{% highlight html %}

//Rotates the 3D Chart 
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc"  Enable3D="true" Rotation="40" ClientIDMode="Static">
    //Set chart type as Column to series
    <CommonSeriesOptions Type="Column" />
    <Size Width="100%" Height="460px"></Size>
 </ej:PivotChart>

{% endhighlight %} 

![](3D-Visualization_images/rotation3d.png)
 
 