---
layout: post
title: Series | OLAPChart | ASP.NET | Syncfusion
description: series
platform: aspnet
control: OLAPChart
documentation: ug
---

#Series

##Series Point customization
By using the `fill` and `border` properties of Chart series, you can customize the OlapChart series color, border color and border width.
 
{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <ClientSideEvents Load="loadTheme" SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            this.model.series[0].points[0].fill = "aqua";
            this.model.series[0].points[0].border = {
                color: "black",
                width: 2
            };
        }
    </script>
</body>

</html>                                           

{% endhighlight %}

![](Series_images/Series_img1.png)