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

## Lazy Loading

Lazy loading feature provides an effective way for loading data on demand by scrolling and viewing a smaller range of data from a larger collection.

{% highlight javascript %}

<ej:Chart ID="Chart1" runat="server"> 
       <PrimaryXAxis>
               // Enable the scroll bar and set the range options
              <ScrollbarSettings Visible="true" CanResize="true">
                   <Range Min="2009/1/1" Max="2014/1/1"></Range>
              </ScrollbarSettings>
          </PrimaryXAxis>
   //..
</ej:Chart>

{% endhighlight %}

![](Performance_images/Perform_img1.png)