---
layout: post
title: Chart-Axes
description: chart axes 
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Chart Axes 

OlapChart typically have two axes that are used to measure and categorize data: a vertical (y) axis and a horizontal (x) axis. By default horizontal (x) axis and vertical (y) axis is added to the Chart with axis labels, gridlines, and tick lines. You can also customize this axis explicitly by adding axis title or removing gridlines, tick lines that are added to the axis by default.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

     &lt;primaryxaxis majorticklines-visible="false" /&gt;

     &lt;primaryyaxis majorticklines-visible="false" /&gt;

&lt;/ej:OlapChart&gt;

Axis Title Customization

Primary axis title font appearance is further customized with the help of the following code example.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

     &lt;primaryxaxis  Title-Text="Primary X title customization" Title-Font-Color="red" Title-Font-FontFamily="Segoe UI" Title-Font-FontStyle="Italic" Title-Font-FontSize="18px" Title-Font-Opacity=1 Title-Font-FontWeight="lighter"/&gt;

     &lt;primaryyaxis Title-Text="Primary Y title customization" Title-Font-Color="red" Title-Font-FontFamily="Segoe UI" Title-Font-FontStyle="Italic" Title-Font-FontSize="18px" Title-Font-Opacity=1 Title-Font-FontWeight="lighter"/&gt;

&lt;/ej:OlapChart&gt;



{ ![](Chart-Axes_images/Chart-Axes_img1.png) | markdownify }
{:.image }


Axis Line

Axis line is drawn in Chart to represent the end of the axis in ChartArea. It is customized with the help of following code example.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

         &lt;primaryxaxis AxisLine-Visible="true" AxisLine-Offset=1 AxisLine-Width=3.5/&gt;

         &lt;primaryyaxis AxisLine-DashArray="2,3"/&gt;

&lt;/ej:OlapChart&gt;



{ ![](Chart-Axes_images/Chart-Axes_img2.png) | markdownify }
{:.image }


Position Opposed

Position of the primary X and Y axis is set to the top with the help opposedPosition property.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

     &lt;primaryxaxis OpposedPosition="true" /&gt;

     &lt;primaryyaxis OpposedPosition="true"/&gt;

&lt;/ej:OlapChart&gt;



{ ![](Chart-Axes_images/Chart-Axes_img3.png) | markdownify }
{:.image }


Appearance Customization 

Background, border color and outer width of the Chart Area is customized with the help of following properties.

Background – sets the background color for Chart Area.

Color – sets the color for the border.

Width – sets the width for the border.





[ASP.NET]

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OLAP Chart in Essential Studio"&gt;

    &lt;chartarea&gt;

        &lt;border color = "red" width= "2" background="aqua"&gt;&lt;/border&gt;

    &lt;/chartarea&gt;

&lt;/ej:OlapChart&gt;

&lt;/asp:Content&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/chartArea.png](Chart-Axes_images/Chart-Axes_img4.png) | markdownify }
{:.image }


