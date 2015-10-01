---
layout: post
title: Chart Types | OLAPChart | ASP.NET Webforms | Syncfusion
description: chart types
platform: aspnet
control: OLAP Chart
documentation: ug
---

# Chart Types

Essential OLAP Chart ASP.NET supports 13 different types of chart as follows:

* Column 
* Stacking Column
* Bar
* Stacking Bar
* Area
* Step Area
* Spline Area
* Stacking Area
* Pie
* Pyramid
* Line
* Step Line
* Spline

## Column Chart


Column Chart is the most commonly used chart types. It uses vertical bars (called columns) to display different values of one or more items. Points from adjacent series are drawn as bars next to each other. It is used to compare the frequency, count, total or average of data in different categories. It is ideal to show the variations in the value of an item over a period of time.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions Type="Column" Tooltip-Visible="true" />

    <Legend  Visible="true" rowcount=3></Legend>

</ej:OlapChart>

{% endhighlight %}


The following screenshot displays a Column Chart.



 ![](Chart-Types_images/Chart-Types_img1.png)



## Stacking Column Chart

Stacking Column Chart is similar to column charts except the “Y-values”. These “Y-values” stack on top of each other in a specified series order. This helps to visualize the relationship of parts to the whole chart.

 {% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="StackingColumn" tooltip-visible="true" />

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}




The following screenshot displays the stacking Column Chart.


![](Chart-Types_images/Chart-Types_img2.png) 


## Bar Chart

The Bar Chart is the simplest and most versatile chart of statistical diagrams. It displays horizontal bars for each point in the series and points from adjacent series. Bar Charts are drawn as bars next to each other. Bar charts are used to compare values across categories, for displaying the variations in the value of an item over time or for comparing the values of several items at a single point in time.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Bar"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>


{% endhighlight %}




The following screenshot displays a Bar Chart.


![](Chart-Types_images/Chart-Types_img3.png) 


## Stacking Bar Chart

Stacking BarChart is a Regularbarchart with the X-values stacked on top of each other in the specified series order.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="StackingBar"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>


 {% endhighlight %}



The following screenshot displays the Stacking Bar Chart.

 ![](Chart-Types_images/Chart-Types_img4.png) 


## Pie Chart

A Pie chart is used to summarize a set of categorical data or displaying different values of a given variable (e.g., percentage distribution). This type of chart is a circle divided into a series of segments. Each segment represents a particular category.


{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Pie"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}


The following screenshot displays a Pie Chart.



 ![](Chart-Types_images/Chart-Types_img5.png) 



## Pyramid Chart

The Pyramid Chart type displays the data in the form of a triangle. It helps you to visualize data in a hierarchical structure without any axes.

 {% highlight html %}




<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Pyramid"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}







The following screen shot displays the Pyramid Chart.


![](Chart-Types_images/Chart-Types_img6.png)



## Line Chart

The Line Chart joins the data points on a plot using straight lines that show trends in data at equal intervals.

 {% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Line"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}


The following screenshot displays the Line Chart.

 ![](Chart-Types_images/Chart-Types_img7.png) 



### Step Line Chart

Step LineChart uses horizontal and vertical lines to connect the data points resulting in a step like progression. 

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="StepLine"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}


The following screenshot displays the Step Line Chart.


 ![](Chart-Types_images/Chart-Types_img8.png) 



## Spline Chart

The spline chart is similar to line charts except it connects different data points using curve lines instead of straight lines.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Spline"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}

The following screenshot displays the Spline Chart.

![](Chart-Types_images/Chart-Types_img9.png) 



## Area Chart

Area Chart emphasizes the degree of change of values over a period of time. Instead of rendering data as discreet bars or columns, an area chart renders it in a continuous ebb-and-flow pattern as defined against the y-axis.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="Area"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

 {% endhighlight %}


The following screenshot displays the Area Chart.

 ![](Chart-Types_images/Chart-Types_img10.png) 


## Step Area Chart

Step Area chart is similar to the regular area chart except for a straight line tracing the shortest path between the data points. The values are connected by continuous vertical and horizontal lines forming a step like progression.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="StepArea"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}


The following screenshot displays a Step Area Chart.

 ![](Chart-Types_images/Chart-Types_img11.png) 



## Spline Area Chart

Spline Area chart is similar to Area Chart with the difference in which the data points of a series are connected. It connects each series of points by a smooth spline curve.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

    <CommonSeriesOptions type="SplineArea"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>


{% endhighlight %}


The following Screenshot displays a Spline Area Chart.

![](Chart-Types_images/Chart-Types_img12.png) 



## Stacking Area Chart

Stacking Area chart is similar to regular area chart except the “Y-values”. These “Y-values” stack on top of each other in the specified series order. This helps to visualize the relationship of parts to the whole data.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" >

<CommonSeriesOptions type="StackingArea"/>

    <Legend visible="true" rowcount="3"></Legend>

</ej:OlapChart>

{% endhighlight %}

The following screenshot displays a Stacking Area Chart.

 ![](Chart-Types_images/Chart-Types_img13.png) 



