---
layout: post
title: Series
description: series
platform: aspnet
control: OLAP Chart
documentation: ug
---

# Series

Series is a collection of series items that contain the actual data points to be displayed on the chart. Series type allows you to customize the chart type whose appearance/style is customized.

## Series Type Customization

A combination Chart combines two or more series types in a single Chart. But there are some limitations in the combination Chart. They are:

1. Can’t combine Column and Bar series.
2. Pie Chart can’t be used with other series types.

 {% highlight html %}

<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

        <CommonSeriesOptions Type="Column" Tooltip-Visible="true"/>

        <ClientSideEvents SeriesRendering="onSeriesRenders"/>

    </ej:OlapChart>

</asp:Content>

<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

    <script type="text/javascript">

        function onSeriesRenders(args) {

            this.model.series[5].type = ej.olap.OlapChart.ChartTypes.Line;

            this.model.series[5].marker.visible = true;

        }

</script>

</asp:Content>

{% endhighlight %}

 ![C:/Users/Tamilarasu .M/Pictures/document/Chart/Customizingchartseries.png](Series_images/Series_img1.png)



## Series Points Customization

OlapChart series is customized using fill, border width and border color. The stroke-width of the line, spline series is customized using width property of series.  The series color is customized using fill property of series. The border color and width of the column/bar is customized using border property of series. And the column/bar chart are customized using the ‘fill’ and ‘border’ property of each point.

 {% highlight html %}

<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

     <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc">

        <CommonSeriesOptions Type="Column"/>

        <ClientSideEvents SeriesRendering="onSeriesRenders" />

    </ej:OlapChart>

</asp:Content>

<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

<script type="text/javascript">

        function onSeriesRenders(args) {

            this.model.series[0].points[0].fill = "aqua";

            this.model.series[0].points[0].border = { color: "black", width: 2 };

        }

</script>

</asp:Content>

{% endhighlight %}

