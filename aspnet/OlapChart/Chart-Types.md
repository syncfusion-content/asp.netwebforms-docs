---
layout: post
title: Chart-Types
description: chart types
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Chart Types

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
### Column Chart


Column Chart is the most commonly used chart types. It uses vertical bars (called columns) to display different values of one or more items. Points from adjacent series are drawn as bars next to each other. It is used to compare the frequency, count, total or average of data in different categories. It is ideal to show the variations in the value of an item over a period of time.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions Type="Column" Tooltip-Visible="true" /&gt;

    &lt;Legend  Visible="true" rowcount=3&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays a Column Chart.



{ ![](Chart-Types_images/Chart-Types_img1.png) | markdownify }
{:.image }


### Stacking Column Chart

Stacking Column Chart is similar to column charts except the “Y-values”. These “Y-values” stack on top of each other in a specified series order. This helps to visualize the relationship of parts to the whole chart.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="StackingColumn" tooltip-visible="true" /&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;






The following screenshot displays the stacking Column Chart.


{ ![](Chart-Types_images/Chart-Types_img2.png) | markdownify }
{:.image }


### Bar Chart

The Bar Chart is the simplest and most versatile chart of statistical diagrams. It displays horizontal bars for each point in the series and points from adjacent series. Bar Charts are drawn as bars next to each other. Bar charts are used to compare values across categories, for displaying the variations in the value of an item over time or for comparing the values of several items at a single point in time.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Bar"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;







The following screenshot displays a Bar Chart.


{ ![](Chart-Types_images/Chart-Types_img3.png) | markdownify }
{:.image }


### Stacking Bar Chart

Stacking BarChart is a Regularbarchart with the X-values stacked on top of each other in the specified series order.


[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="StackingBar"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays the Stacking Bar Chart.

{ ![](Chart-Types_images/Chart-Types_img4.png) | markdownify }
{:.image }


### Pie Chart

A Pie chart is used to summarize a set of categorical data or displaying different values of a given variable (e.g., percentage distribution). This type of chart is a circle divided into a series of segments. Each segment represents a particular category.


[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Pie"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;









The following screenshot displays a Pie Chart.



{ ![](Chart-Types_images/Chart-Types_img5.png) | markdownify }
{:.image }


### Pyramid Chart

The Pyramid Chart type displays the data in the form of a triangle. It helps you to visualize data in a hierarchical structure without any axes.


[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Pyramid"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;









The following screen shot displays the Pyramid Chart.


{ ![](Chart-Types_images/Chart-Types_img6.png) | markdownify }
{:.image }


### Line Chart

The Line Chart joins the data points on a plot using straight lines that show trends in data at equal intervals.


[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Line"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;















The following screenshot displays the Line Chart.

{ ![](Chart-Types_images/Chart-Types_img7.png) | markdownify }
{:.image }


### Step Line Chart

Step LineChart uses horizontal and vertical lines to connect the data points resulting in a step like progression. 



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="StepLine"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays the Step Line Chart.


{ ![](Chart-Types_images/Chart-Types_img8.png) | markdownify }
{:.image }


### Spline Chart

The spline chart is similar to line charts except it connects different data points using curve lines instead of straight lines.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Spline"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays the Spline Chart.

{ ![](Chart-Types_images/Chart-Types_img9.png) | markdownify }
{:.image }


### Area Chart

Area Chart emphasizes the degree of change of values over a period of time. Instead of rendering data as discreet bars or columns, an area chart renders it in a continuous ebb-and-flow pattern as defined against the y-axis.


[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="Area"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays the Area Chart.

{ ![](Chart-Types_images/Chart-Types_img10.png) | markdownify }
{:.image }


### Step Area Chart

Step Area chart is similar to the regular area chart except for a straight line tracing the shortest path between the data points. The values are connected by continuous vertical and horizontal lines forming a step like progression.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="StepArea"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays a Step Area Chart.

{ ![](Chart-Types_images/Chart-Types_img11.png) | markdownify }
{:.image }


### Spline Area Chart

Spline Area chart is similar to Area Chart with the difference in which the data points of a series are connected. It connects each series of points by a smooth spline curve.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

    &lt;CommonSeriesOptions type="SplineArea"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following Screenshot displays a Spline Area Chart.

{ ![](Chart-Types_images/Chart-Types_img12.png) | markdownify }
{:.image }


### Stacking Area Chart

Stacking Area chart is similar to regular area chart except the “Y-values”. These “Y-values” stack on top of each other in the specified series order. This helps to visualize the relationship of parts to the whole data.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" &gt;

&lt;CommonSeriesOptions type="StackingArea"/&gt;

    &lt;Legend visible="true" rowcount="3"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;











The following screenshot displays a Stacking Area Chart.

{ ![](Chart-Types_images/Chart-Types_img13.png) | markdownify }
{:.image }


