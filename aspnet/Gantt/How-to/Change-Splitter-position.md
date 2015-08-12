---
layout: post
title: Change-Splitter-position
description: change splitter position
platform: aspnet
control: Gantt
documentation: ug
---

## Change Splitter position

In Gantt control, Splitter separates the Treegrid section from the Chart section. 

 ![C:/Users/labuser/Desktop/splitter.png](Change-Splitter-position_images/Change-Splitter-position_img1.png) 



It is possible to change the position of the Splitter while loading the Gantt by using the SplitterPosition property, thereby varying the width of the Treegrid and Chart sections in the control.  SplitterPosition property denotes the percentage of the Treegrid section’s width to be rendered and this property supports both pixels and percentage values.

The following code example explains how to define the SplitterPosition property in the Gantt.





{% highlight html %}



<ej:Gantt ID="gantt" runat="server" SplitterPosition="50%">

        // ...

        //also you can define with pixel value as 

        // ‘ SplitterPosition=”650” ’ (or) ‘ SplitterPosition=”650px” ’

)</ej:Gantt>



{% endhighlight %}



[C:/Users/labuser/Desktop/splitter30.png](Change-Splitter-position_images/Change-Splitter-position_img2.png) 







[C:/Users/labuser/Desktop/Splitter50.png](Change-Splitter-position_images/Change-Splitter-position_img3.png) 



[C:/Users/labuser/Desktop/Splitter600px.png](Change-Splitter-position_images/Change-Splitter-position_img4.png)





