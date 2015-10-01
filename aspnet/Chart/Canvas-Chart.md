---
layout: post
title: Canvas Chart | Chart | ASP.NET Webforms | Syncfusion
description: canvas chart
platform: aspnet
control: Chart
documentation: ug
---

# Canvas Chart

Essential Chart provides canvas rendering support in Html5. By default, Chart renders in SVG(Scalable Vector Graphics). When you enable the EnableCanvasRendering option in model, then the chart renders in canvas. Canvas chart is used for fast rendering when using large amount of data points.  And also you can export the canvas chart as an image for further use. All user interaction provided by Essential Chart can be done in canvas rendering. Canvas chart does not support 3D and animation functionalities that can be done in SVG rendering.
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...



   </ej:Chart>


{% endhighlight  %}


The following screenshot illustrates the canvas chart

![C:/Users/ApoorvahR/Desktop/1.png](Canvas-Chart_images/Canvas-Chart_img1.png)




