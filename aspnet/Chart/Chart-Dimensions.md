---
layout: post
title: Chart Dimensions | Chart | ASP.NET Webforms | Syncfusion
description: chart dimensions
platform: aspnet
control: Chart
documentation: ug
---

# Chart Dimensions

You can set the size of the chart directly on the chart or to the container of the chart. When you do not specify the size, it takes 450px as the height and window size as its width, by default. 

## Set size for the container

You can customize the chart dimension by setting the width and height for the container element. 

{% highlight html %}

<ej:Chart ID="Chart1" runat="server" Width="820" Height="500">    
</ej:Chart>

{% endhighlight %}


## Set size in pixels

You can also set the chart dimension by using the **Size** property of the chart. 

{% highlight html %}


<ej:Chart ID="Chart1" runat="server">    
    <Size Width="600" Height="450"></Size>
</ej:Chart>

{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img1.png)


## Setting size relative to the container size

You can specify the chart size in percentage by using the Size property. The chart gets its dimension with respect to its container.

{% highlight html %}

<div id="Chart1" style="width:700px; height:500px">  
   <ej:Chart ID="Chart1" runat="server">    
       <Size Width="80%"></Size>
   </ej:Chart>
</div>


{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the **IsResponsive** property to **true**, where the chart adapts to the changes in size of the container.

{% highlight html %}

   <ej:Chart ID="Chart1" runat="server" IsResponsive="true">    
   </ej:Chart>

{% endhighlight %} 
