---
layout: post
title: Chart Axes | NumericTextbox | ASP.NET Webforms | Syncfusion
description: chart axes 
platform: aspnet
control: OLAP Chart
documentation: ug
---

# Chart Axes 

OlapChart typically have two axes that are used to measure and categorize data: a vertical (y) axis and a horizontal (x) axis. By default horizontal (x) axis and vertical (y) axis is added to the Chart with axis labels, gridlines, and tick lines. You can also customize this axis explicitly by adding axis title or removing gridlines, tick lines that are added to the axis by default.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

     <primaryxaxis majorticklines-visible="false" />

     <primaryyaxis majorticklines-visible="false" />

</ej:OlapChart>

{% endhighlight %}

## Axis Title Customization

Primary axis title font appearance is further customized with the help of the following code example.

{% highlight html %}



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

     <primaryxaxis  Title-Text="Primary X title customization" Title-Font-Color="red" Title-Font-FontFamily="Segoe UI" Title-Font-FontStyle="Italic" Title-Font-FontSize="18px" Title-Font-Opacity=1 Title-Font-FontWeight="lighter"/>

     <primaryyaxis Title-Text="Primary Y title customization" Title-Font-Color="red" Title-Font-FontFamily="Segoe UI" Title-Font-FontStyle="Italic" Title-Font-FontSize="18px" Title-Font-Opacity=1 Title-Font-FontWeight="lighter"/>

</ej:OlapChart>

{% endhighlight %}

 ![](Chart-Axes_images/Chart-Axes_img1.png) 



## Axis Line

Axis line is drawn in Chart to represent the end of the axis in ChartArea. It is customized with the help of following code example.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

         <primaryxaxis AxisLine-Visible="true" AxisLine-Offset=1 AxisLine-Width=3.5/>

         <primaryyaxis AxisLine-DashArray="2,3"/>

</ej:OlapChart>

{% endhighlight %}

 ![](Chart-Axes_images/Chart-Axes_img2.png)



## Position Opposed

Position of the primary X and Y axis is set to the top with the help opposedPosition property.

 {% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

     <primaryxaxis OpposedPosition="true" />

     <primaryyaxis OpposedPosition="true"/>

</ej:OlapChart>

{% endhighlight %}

![](Chart-Axes_images/Chart-Axes_img3.png)



## Appearance Customization 

Background, border color and outer width of the Chart Area is customized with the help of following properties.

Background – sets the background color for Chart Area.

Color – sets the color for the border.

Width – sets the width for the border.



 {% highlight html %}

<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OLAP Chart in Essential Studio">

    <chartarea>

        <border color = "red" width= "2" background="aqua"></border>

    </chartarea>

</ej:OlapChart>

</asp:Content>

 {% endhighlight %}

 ![C:/Users/Tamilarasu .M/Pictures/document/Chart/chartArea.png](Chart-Axes_images/Chart-Axes_img4.png) 



