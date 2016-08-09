---
layout: post
title: Chart Types | PivotChart | ASP.NET | Syncfusion
description: chart types
platform: aspnet
control: PivotChart
documentation: ug
---

# Chart Types

Essential **PivotChart ASP.NET** supports 14 different types of chart as follows:

* Column
* Stacking Column
* Bar
* Stacking Bar
* Pie
* Pyramid
* Funnel
* Line
* Step Line
* Spline
* Area
* Step Area
* Spline Area
* Stacking Area

## Column Chart

**Column Chart** is the most commonly used chart type. It uses vertical bars (called columns) to display different values of one or more items. Points from adjacent series are drawn as bars next to each other. It is used to compare the frequency, count, total or average of data in different categories. It is ideal to show the variations in the value of an item over a period of time.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions Type="Column" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screenshot displays a **Column Chart**.

![](Chart-Types_images/Chart-Types_img1.png)

Column chart
{:.caption}

## Stacking Column Chart

**Stacking Column** Chart is similar to column charts except the Y-values. These Y-values stack on top of each other in a specified series order. This helps to visualize the relationship of parts to whole across categories.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="StackingColumn" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screenshot displays the **stacking Column Chart**.


![](Chart-Types_images/Chart-Types_img2.png) 

Stacking Column Chart
{:.caption}

## Bar Chart

The **Bar Chart** displays horizontal bars for each point in the series and points from adjacent series. Bar charts are used to compare values across categories, for displaying the variations in the value of an item over time or for comparing the values of several items at a single point in time.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Bar"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screenshot displays a **Bar Chart**.

![](Chart-Types_images/Chart-Types_img3.png) 

Bar Chart
{:.caption}

## Stacking Bar Chart

**Stacking Bar Chart** is a regular **bar** chart with the X-values stacked on top of each other in the specified series order.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="StackingBar"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screenshot displays the **Stacking Bar Chart**.

![](Chart-Types_images/Chart-Types_img4.png) 

Stacking Bar Chart
{:.caption}

## Pie Chart

A **Pie chart** is used to summarize a set of categorical data or displaying different values of a given variable (e.g., percentage distribution). This type of chart is a circle divided into a series of segments. Each segment represents a particular category.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Pie"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following screenshot displays a **Pie Chart**.

![](Chart-Types_images/Chart-Types_img5.png) 

Pie Chart
{:.caption}

## Pyramid Chart

The **Pyramid Chart** type displays the data in the form of a triangle. It helps you to visualize data in a hierarchical structure without any axes.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Pyramid"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screen shot displays the **Pyramid Chart**.


![](Chart-Types_images/Chart-Types_img6.png)

Pyramid Chart
{:.caption}


## Funnel Chart

The **Funnel Chart**  type displays the data in the form of an inverted triangle. It helps you to visualize data in a hierarchical structure without any axes.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Funnel"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

The following screen shot displays the **Funnel Chart**.


![](Chart-Types_images/Chart-Types_img14.png)

Funnel Chart
{:.caption}

## Line Chart

The **Line Chart** joins the data points on a plot using straight lines that show trends in data at equal intervals.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Line"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following screenshot displays the **Line Chart**.

![](Chart-Types_images/Chart-Types_img7.png) 

Line Chart
{:.caption}

## Step Line Chart

**Step Line Chart** uses horizontal and vertical lines to connect the data points resulting in a step like progression. 

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="StepLine"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following screenshot displays the **Step Line Chart**.

![](Chart-Types_images/Chart-Types_img8.png) 

Step Line Chart
{:.caption}

## Spline Chart

The **Spline Chart** is similar to line charts except it connects different data points using curve lines instead of straight lines.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Spline"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

The following screenshot displays the **Spline Chart**.

![](Chart-Types_images/Chart-Types_img9.png) 

Spline Chart
{:.caption}

## Area Chart

**Area Chart** emphasizes the degree of change of values over a period of time. Instead of rendering data as discrete bars or columns, an area chart renders it in a continuous ebb-and-flow pattern as defined against the y-axis.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="Area"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following screenshot displays the **Area Chart**.

![](Chart-Types_images/Chart-Types_img10.png) 

Area Chart
{:.caption}

## Step Area Chart

**Step Area** chart is similar to the regular area chart except for a straight line tracing the shortest path between the data points. The values are connected by continuous vertical and horizontal lines forming a step like progression.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="StepArea"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following screenshot displays a **Step Area Chart**.

![](Chart-Types_images/Chart-Types_img11.png) 

Step Area Chart
{:.caption}

## Spline Area Chart

**Spline Area** chart is similar to Area Chart with the difference in which the data points of a series are connected. It connects each series of points by a smooth **spline curve**.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="SplineArea"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}


The following Screenshot displays a **Spline Area Chart**.

![](Chart-Types_images/Chart-Types_img12.png) 

Spline Area Chart
{:.caption}

## Stacking Area Chart

**Stacking Area** chart is similar to regular area chart except the “Y-values”. These “Y-values” stack on top of each other in the specified series order. This helps to visualize the relationship of parts to whole across categories.

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions type="StackingArea"/>
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>

{% endhighlight %}

The following screenshot displays a **Stacking Area Chart**.

![](Chart-Types_images/Chart-Types_img13.png) 

Stacking Area Chart
{:.caption}


## combination Chart 

A **combination Chart** combines two or more series types in a single Chart. But there are some limitations in the combination Chart. They are:

1. Can’t combine Column and Bar series.
2. Pie Chart can’t be used with other series types.



{% highlight CSHTML %}

<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" >
    <CommonSeriesOptions Type="Column" />
    <ClientSideEvents Load="loadTheme" SeriesRendering="onSeriesRenders" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
    
<script>
function onSeriesRenders(args) {
    this.model.series[5].type = ej.PivotChart.ChartTypes.Line;
    this.model.series[5].marker.visible = true;
}
</script>

{% endhighlight %}

The following screenshot displays a **combination Chart**.

![](Chart-Types_images/combinationalchart.png)
