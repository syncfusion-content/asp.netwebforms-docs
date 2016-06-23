---
title: Date, Appointment, and View navigation
description: Navigation between views, appointments, and date
platform: aspnet
control: schedule
documentation: ug
keywords: view navigation, date navigation, appointment navigation 
---
# Navigation

Navigation in Scheduler can be classified based on Scheduler views, date and also the appointments in it.

## View Navigation

By default, all the [available view options](/aspnet/schedule/views) except the `Custom View` are available at the top right corner of the Schedule header, which can be traverse through continuously as and when needed.  

Clicking on the particular date header in the Week/Work Week/Month/Custom View will navigate to the day view automatically. Also, clicking on the week header ranges displayed at the left side in the month view will navigate to the Week view. These particular actions can take place only if the Week and Day view options are present in the `Views` Collection.

### Handling View navigation actions

Usually, the `Navigation` event gets triggered whenever the views/dates are being navigated. To block the navigation to day and week views from month view, the **Navigation** event can be used in the following way.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" Navigation="onNavigation">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        //args.target.currentTarget – target element which is clicked.
        function onNavigation(args) {
            if (args.requestType == "viewNavigate" && (target.hasClass("e-headercells") || target.hasClass("e-monthheader") || target.hasClass("e-timecells")))
                args.cancel = true;
        }
    </script>
</asp:Content>

{% endhighlight %}

N> Based on the navigation, the appointments that lies between the particular date ranges of the current view are fetched and rendered in the Scheduler.

## Date Navigation

The Scheduler date can be navigated on two aspects either in a continuous or random manner. On pressing the previous and next navigation arrow icons in the Scheduler header will move the scheduler one date back and forth respectively.

Another way of navigating through date is by making use of the built-in calendar available within the Scheduler, which pops out when the header date range is clicked. Selecting any date in the calendar will make the Scheduler to move to that particular date appropriately.

### Handling Date Navigation actions

To handle the date navigation actions, the `Navigation` event can be used. For example, to block the date navigation, follow the below code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" Navigation="onNavigation">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onNavigation(args) {
            //args.target – target element which is clicked.
            //args.currentDate – current date of the Scheduler.
            //args.requestType – Specifies the navigation type.
            if (args.requestType == "dateNavigate")
                args.cancel = true;
        }
    </script>
</asp:Content>

{% endhighlight %}

## Appointment Navigation

The Appointment navigation bars (labeled **Previous/Next Appointment**) are rendered parallel to each other on the left and right centric corners of the Schedule control. It is controlled by an API `ShowAppointmentNavigator` which is set to true by default. When it is set to false, these bars will not be displayed on the Scheduler.

Whenever the Previous/Next Appointment bars are clicked, it navigates the Scheduler to the corresponding closest date where the appointments are available. If no appointments are available beyond the current date, then these appointment bars will be in a disabled state.      

The following code example shows the way to define the **ShowAppointmentNavigator** property for Scheduler.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" ShowAppointmentNavigator="true" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

