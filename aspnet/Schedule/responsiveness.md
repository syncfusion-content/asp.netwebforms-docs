---
title: Schedule - Responsiveness
description: This section explains the responsive behavior of the Syncfusion ASP.NET Web Forms Schedule control based on the client browser width and height.
platform: aspnet
control: schedule
documentation: ug
keywords: responsive, responsiveness, auto size 
---
# Responsiveness

Scheduler is provided with default **responsive** support, so that it adjust or auto-resize it’s UI content based on the window or the container size on which it is placed. 

## Auto-Resizing Scheduler

By default, setting 100% width to the Scheduler makes it adaptable to the window or its parent container, as and when the browser is resized. This will not allow the scheduler to adapt height-wise.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> When the Scheduler width is set to have **less** **than** **600px**, then the View selection options will be displayed in a **navigation** **drawer**.  

Also, whenever the Scheduler resizes - the width of the work cells adjusts automatically (if no **CellWidth** property is specified with pixel values), but the height of the cells are kept to remain as same as 20px until **CellHeight** property is set explicitly with some pixel values.

## Scheduler in Mobile/Tablets

The Scheduler layout adapts automatically in the mobile and tablet devices with the appropriate UI changes, as the `IsResponsive` property is set to **true** by default. In case, if the user wants to display the normal scheduler in mobile devices without any adaptive enhancements, then the `IsResponsive` property can be set to false.

Some of the default changes done for adaptive Scheduler to render in mobile devices are as follows,

* Animation effect introduced between view/date navigation.
* Cell Height increased
* The header date display changes (displayed next to the navigation icons).
* View options displayed in Navigation drawer
* Time cell width decreased
* Quick window display blocked on cell/appointment single click.
* Appointment resizing action blocked.
* Multiple cell selection blocked.
* Delete appointment option made available within the appointment window.
* Week header display in month view hidden.
* With Multiple resources - only one resource is viewable initially on the screen and to further look onto other resources, user need to swipe the screen.

N> To make the Scheduler control to react as responsive in mobile/tablet devices, it is necessary to refer the additional [ej.responsive.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css) file in the application.

The following code snippet depicts the Scheduler code with responsive set to true.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" IsResponsive="true" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource

{% endhighlight %}

