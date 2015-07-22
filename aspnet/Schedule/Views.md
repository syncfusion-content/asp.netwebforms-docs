---
layout: post
title: Views
description: views
platform: aspnet
control: Schedule
documentation: ug
---

# Views

##View Customization

* The views option in the Schedule control is a collection that allows you to add/remove the view items to it. The items that are added to it is displayed in the date-header section of the Schedule control.
* It accepts the following string array collections:
1. Day
2. Week
3. WorkWeek
4. Month
5. CustomView

The following code example describes how to customize the display of view options of the Schedule control.

{% highlight html %}




<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014"

Views="Week,Month">



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

* The following screenshot displays the output of the above code with the view customizations by displaying only two views namely Week and Workweek in the toolbar.

![](Views_images/Views_img1.png)


_Figure_ _84_: schedule with view customization._

##Current View

* By default, the Schedule control is displayed with the Week view. It is possible to change the current view of the Schedule control by setting the currentView option with the required view name. 
* The valid enum values that are accepted by currentView property are as follows,
1. ej.Schedule.CurrentView.Day
2. ej.Schedule.CurrentView.Week
3. ej.Schedule.CurrentView.Workweek
4. ej.Schedule.CurrentView.Month
5. ej.Schedule.CurrentView.CustomView
* By setting CustomView option to the currentView property, the dates specified as the start and end in the renderDates object are rendered in the Schedule

The following code example explains how to change the current view of the Schedule control.


{% highlight html %}



<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px"

CurrentDate="5/2/2014"

CurrentView="Day">



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>



</ej:Schedule>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

* Execute the above code to render the following screenshot that displays day view as the currentView of the Schedule control,

![](Views_images/Views_img2.png)


   _Figure_ _85_:  schedule with current view._

Custom Date Rendering

* It is possible to render only the user-specified date ranges in the Schedule control by using the renderDates property. 
* To render the Schedule control with specific date ranges, it is necessary to specify the start and end dates as follows.


{% highlight html %}




<!-- Set the currentView as customView in order to render the custom dates -->>

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentView="CustomView" CurrentDate="5/2/2014" Views="Day,Week,WorkWeek,Month,CustomView" >



<RenderDates Start="11/07/2014" End="12/10/2014" />



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>



</ej:Schedule>



<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>" SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>



{% endhighlight %}

The output of the above code example is as follows.

![](Views_images/Views_img3.png)




Important: When the date ranges specified in the renderDates property yield more than the difference of 7 days, then the schedule is rendered in the month-like view with the user provided dates. When the date difference yields less than 7, then the schedule gets rendered in the normal view with the specified dates.



