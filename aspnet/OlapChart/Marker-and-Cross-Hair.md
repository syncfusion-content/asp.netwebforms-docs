---
layout: post
title: Marker-and-Cross-Hair
description: marker and cross hair 
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Marker and Cross Hair 

Markers are the symbols that represent on the series of the Chart Area. Cross Hair helps you to view the value at mouse position or touch contact point.

Real-time use of Cross Hair

You can view the information while moving the mouse pointer over the Chart Area with the help of CrossHair. For example, in a line chart you can get exact values of x and y axis while moving the mouse on Chart Area.



{ ![](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img1.png) | markdownify }
{:.image }


Marker Shape Customization 

In OlapChart, you can customize the marker shape with different symbols like rectangle, circle, cross, diamond, pentagon, hexagon, star, ellipse, triangle etc.



[ASP.NET] 

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

     &lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

         &lt;CommonSeriesOptions Type="line"/&gt;

         &lt;ClientSideEvents SeriesRendering="onSeriesRenders" /&gt;

     &lt;/ej:OlapChart&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

    &lt;script type="text/javascript"&gt;

        function onSeriesRenders(args) {

            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)

                this.model.series[seriescount].marker.shape = "Triangle";

        }



&lt;/script&gt;

&lt;/asp:Content&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/markershape.png](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img2.png) | markdownify }
{:.image }


Cross Hair Customization 

In order to view the value at mouse position or touch contact point, you can use the crosshair property. You can customize the appearance using the following code example. 



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"&gt;

     &lt;PrimaryXAxis CrosshairLabel-Visible="true" /&gt;

     &lt;PrimaryYAxis CrosshairLabel-Visible="true"/&gt;

     &lt;Crosshair Visible="true" Type="Crosshair" line-width="2" line-color="red"/&gt;

&lt;/ej:OlapChart&gt;





{ ![](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img3.png) | markdownify }
{:.image }


