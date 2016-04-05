---
layout: post
title: Performance tips | ASP.NET Webforms | Syncfusion
description: How to improve the performance of Essential JavaScript Chart
platform: aspnet
control: Chart
documentation: ug
---

# Performance 

* When there are large number of points to load, you can enable canvas rendering mode in chart. Canvas rendering is faster than SVG because it does not involve manipulating DOM elements as much as SVG rendering.   

{% highlight html %}

<ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true"> 
   
</ej:Chart>

{% endhighlight %}

[Click](http://asp.syncfusion.com/demos/web/chart/loadpoints.aspx) here to view the online demo sample that shows Chart performance with 100,000 data points.


* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** and **Tooltip** to view point information.

