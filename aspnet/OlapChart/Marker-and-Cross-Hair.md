---
layout: post
title: Marker and Cross Hair | OLAPChart | ASP.NET | Syncfusion
description: marker and cross hair 
platform: aspnet
control: OLAPChart
documentation: ug
---

# Marker and Cross Hair 

Markers are the symbols that represent on the series of the Chart Area. Cross Hair helps you to view the value at mouse position or touch contact point.

## Real-time use of Cross Hair

You can view the information while moving the mouse pointer over the Chart Area with the help of CrossHair. For example, in a line chart you can get exact values of x and y axis while moving the mouse on Chart Area.

![](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img1.png) 

Real time use of Cross Hair
{:.caption}

## Marker Shape Customization 

In OlapChart, you can customize the marker shape with different symbols like rectangle, circle, cross, diamond, pentagon, hexagon, star, ellipse, triangle etc.

{% highlight html %}
<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

     <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

         <CommonSeriesOptions Type="line"/>

         <ClientSideEvents SeriesRendering="onSeriesRenders" />

     </ej:OlapChart>

</asp:Content>

<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

    <script type="text/javascript">

        function onSeriesRenders(args) {

            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)

                this.model.series[seriescount].marker.shape = "Triangle";

        }



</script>

</asp:Content>
{% endhighlight %}

![](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img2.png)

Marker Shape Customization
{:.caption}

## Cross Hair Customization 

In order to view the value at mouse position or touch contact point, you can use the crosshair property. You can customize the appearance using the following code example. 

{% highlight html %}
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

<PrimaryXAxis CrosshairLabel-Visible="true" />

<PrimaryYAxis CrosshairLabel-Visible="true"/>

<Crosshair Visible="true" Type="Crosshair" line-width="2" line-color="red"/>

</ej:OlapChart>
{% endhighlight %}

![](Marker-and-Cross-Hair_images/Marker-and-Cross-Hair_img3.png) 

Cross Hair Customization
{:.caption}
