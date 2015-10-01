---
layout: post
title: Task Relationship | Gantt | ASP.NET Webforms | Syncfusion
description: task relationship
platform: aspnet
control: Gantt
documentation: ug
---

# Task Relationship

You can show the relationship between two tasks in Gantt control. These relationships are categorized into four types based on the start and finish date of the task.

*  Start to Start(SS)

You cannot start a task until the other task also starts.

![C:/Users/Rajasekar/Desktop/SS.png](Task-Relationship_images/Task-Relationship_img1.png) 



* Start to Finish(SF)

You cannot finish a task until the other task is started.

![C:/Users/Rajasekar/Desktop/SF.png](Task-Relationship_images/Task-Relationship_img2.png)



* Finish to Start(FS)

You cannot start a task until the other task is completed.

![C:/Users/Rajasekar/Desktop/FS.png](Task-Relationship_images/Task-Relationship_img3.png)





* Finish to Finish(FF)

You cannot finish a task until the other task is completed.

![C:/Users/Rajasekar/Desktop/FF.png](Task-Relationship_images/Task-Relationship_img4.png)



The following code example shows you how to show the predecessor in the Gantt control.



{% highlight html %}

<ej:Gantt ID="GanttContainer" runat="server" 

         PredecessorMapping="Predecessor">

</ej:Gantt>



{% endhighlight %}



The following screenshot displays the output of the above code. 



![](Task-Relationship_images/Task-Relationship_img5.png)

Task relationship
{:.caption}

