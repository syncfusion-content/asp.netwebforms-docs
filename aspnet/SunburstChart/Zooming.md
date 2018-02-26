---
layout: post
title: Sunburst Zooming
description: Learn how to Zoom the SunburstChart for better data visualization
platform: aspnet
control: Sunburst Chart
documentation: ug
---

# Zooming

Sunburst chart provides zooming (drill down) experience with animation for both mouse and touch enabled devices. It allows you to virtualizing the large sets of data into minimum data view.The zooming is achieved by using the property of *zoomSettings*

The following code shows how to initialize the zooming.

{% highlight js %}
<ej:SunburstChart  ID="container" runat="server"> 
<ZoomSettings Enable="true" />                            
</ej:SunburstChart> 


{% endhighlight %}

![](Zooming_images/Zooming_img1.gif)

## Zooming toolbar
By default, zooming toolbar will be enabled while zooming the segment.It contains both back and reset option.
You can align the zooming toolbar position by using *ToolbarHorizontalAlignment* and *ToolbarVerticalAlignment* property.


{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<ZoomSettings Enable="true" ToolbarHorizontalAlignment="left" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Zooming_images/Zooming_img2.png)

[Click](http://asp.syncfusion.com/demos/web/sunburstchart/zooming.aspx) here to view the Zooming sample of the  Sunburst Chart.
