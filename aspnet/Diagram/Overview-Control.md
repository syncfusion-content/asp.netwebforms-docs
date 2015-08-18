---
layout: post
title: Overview-Control
description: overview control
platform: aspnet
control: Diagram
documentation: ug
---

# Overview Control

Overview control allows you to see a preview or an overall view of the entire content of a Diagram. This helps you to look at the overall picture of a large Diagram and also to navigate, pan, or zoom a particular position of the page.

When you work on a very large Diagram, you may not know the part you are actually working on or navigation from one part to another might be difficult. One solution for navigation is to zoom out of the entire Diagram and find where you are. Then you can zoom in to a particular area where you want to be. This solution is not suitable when you need frequent navigations.

Overview control solves these problems by showing you a preview, that is, an overall view of the entire Diagram. A rectangle indicates viewport of the diagram. Navigation becomes easy by dragging this rectangle.

The following code illustrates how to create overview control.

{% highlight html %}

//Initializes overview

<ej:Overview ID="OverviewControl" runat="server" Height="300px" Width="233px" SourceId="DiagramWebControl1"></ej:Overview>   

     </div>

</div>

//Initializes Diagram

<ej:Diagram ID="DiagramWebControl1" runat="server" Height="400px" Width="700px"></ej:Diagram>





{% endhighlight %}



 ![C:/Users/swarneshk/AppData/Local/Microsoft/Windows/INetCache/Content.Word/overview final.png](Overview-Control_images/Overview-Control_img1.png)


_Overview_
