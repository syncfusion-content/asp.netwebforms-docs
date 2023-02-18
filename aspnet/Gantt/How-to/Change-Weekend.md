---
layout: post
title: Change Weekend | Gantt | ASP.NET Webforms | Syncfusion
description: Learn here about how to change workweek/working days in Syncfusion Essential ASP.NET Gantt Control, its elements, and more.
platform: aspnet
control: Gantt
documentation: ug
---

# Change workweek/Weekend in ASP.NET Gantt 
Non-working days/weekend are used to represent the non-productive days in a project. It is possible to change the non-working days in a week using the `WorkWeek` property in Gantt.

By default, Saturdays and Sundays are considered as non-working days/weekend in a project. 

The following code example explains how to change weekend/non-working days

{% highlight html %}

<ej:Gantt ID="gantt" runat="server" WorkWeek="Sunday,Monday,Tuesday,Wednesday,Thursday">
      
</ej:Gantt>
{% endhighlight %}

The above code example makes Fridays and Saturdays as non-working days in a week.

![Change workweek/Weekend in ASP.NET Gantt ](Change-Workweek_images/Change_Workweek_img1.png)

The above screen shot will be displayed after changing the non-working days in Gantt.
{:.caption}




