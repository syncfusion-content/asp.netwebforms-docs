---
layout: post
title: Editing
description: editing
platform: aspnet
control: Gantt
documentation: ug
---

## Editing

The Gantt control provides built-in support to add, insert and update the task inside Gantt. Gantt provides three types of editing, they are:

* Cell Editing
* Normal Editing
* Taskbar Editing
* Predecessor Editing



Cell Editing

Update the task details through grid cell editing by setting EditMode as CellEditing.

The following code example shows you how to enable CellEditing in Gantt control.



{% highlight html %}

<ej:Gantt ID="GanttContainer" runat="server" > //…

        <EditSettings AllowEditing="true" EditMode="cellEditing" />

    </ej:Gantt>





{% endhighlight %}



The output of Gantt with CellEditing is as follows.



{ ![](Editing_images/Editing_img1.png) | markdownify }
{:.image }


Normal Editing

Update the task details through edit dialog by setting EditMode as normal.

The following code example shows you how to enable normal editing in Gantt control.

{% highlight html %}



<ej:Gantt ID="GanttContainer" runat="server"> //…

        <EditSettings AllowEditing="true" EditMode="normal" />

 </ej:Gantt>



{% endhighlight %}



The following screenshot shows the output of normal editing.



{ ![C:/Users/pongeetha/Desktop/NormalEditing.png](Editing_images/Editing_img2.png) | markdownify }
{:.image }


Taskbar Editing

Update the task details by interactions such as resizing and dragging the taskbar. The following code example shows you how to enable taskbar resizing in Gantt control.



{% highlight html %}



<ej:Gantt ID="GanttContainer" runat="server" AllowGanttChartEditing="true">

</ej:Gantt>



{% endhighlight %}





Predecessor Editing

Update the predecessor details of a task using mouse interactions. The following code example shows how to enable predecessor editing.





{% highlight html %}



<ej:Gantt ID="Gantt" runat="server" 

          AllowGanttChartEditing="true"

          PredecessorMapping="predecessor">



 </ej:Gantt>



{% endhighlight %}



The following screen shot shows the predecessor editing in Gantt control.

{ ![C:/Users/labuser/Desktop/hello.png](Editing_images/Editing_img3.png) | markdownify }
{:.image }


_Figure_ _39__: Predecessor Editing_

