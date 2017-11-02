---
layout: post
title: Serial Number | Gantt | ASP.NET Webforms | Syncfusion
description: serial number
platform: aspnet
control: Gantt
documentation: ug
---

# Serial Number

## How to enable Serial number column in Gantt?

The Serial number support in Gantt control provides the sequential order structure for all the available collections of tasks in Gantt chart. The Serial number column can be enabled in Gantt control, with the help of enableSerialNumber property by assigning the “true” value to it. While enabling this property Serial number column will be included and Task Id column will be hidden as well as the default behavior of “Predecessor” column will be changed. In general Predecessor column will be rendered and updated with the value of “Task Id”. But on enabling Serial number support, it will be rendered and updated with the value of “Serial number” of corresponding tasks.

Code snippets for enabling Serial number:






{% highlight html %}



<div style="width:100%;height:100%;overflow:visible;">                  



   <ej:Gantt ID="GanttSerialNumber" runat="server" EnableSerialNumber="true">



   </ej:Gantt>        



</div>   





{% endhighlight %}



The following screenshot displays the Serial number column in Gantt control.



![](Serial-Number_images/Serial_img1.png) 

Figure : Serial Number
{:.caption}


