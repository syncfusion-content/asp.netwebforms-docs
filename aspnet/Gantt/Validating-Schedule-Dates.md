---
layout: post
title: Validating Schedule Dates | Gantt | ASP.NET Webforms | Syncfusion
description: validating schedule dates
platform: aspnet
control: Gantt
documentation: ug
---

# Validating Schedule Dates

Validating schedule dates is used to change the schedule start date and end date dynamically. By this support, ScheduleStartDate and ScheduleEndDate can be automatically updated from the data source. When you change the date of any task item to the date that is beyond ScheduleStartDate or ScheduleEndDate through cell editing, taskbar editing, dialog editing or toolbar operation, then the ScheduleStartDate and ScheduleEndDate can be dynamically updated based on that task item’s date.

PrevTimeSpan and NextTimeSpan toolbar items are used to create new time span based on the schedule mode.





{% highlight html %}



<ej:Gantt ID="gantt" runat="server"

<!— ScheduleStartDate=”02/01/2014” ScheduleEndDate=”03/14/2015” --!> >

// ...

       <ToobarSettings ShowToolbar="true" 

                            ToolbarItems="PrevTimeSpan,NextTimeSpan"/>

        // ...

   </ej:Gantt>



{% endhighlight %}


The following screenshot illustrates the output of the above code.

![](Validating-Schedule-Dates_images/Validating-Schedule-Dates_img1.png)


Validating schedule dates
{:.caption}
