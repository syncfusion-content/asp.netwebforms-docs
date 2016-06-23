---
title: Schedule - Context Menu	
description: Default and Custom context menu options for appointments and cells in Scheduler
platform: aspnet
control: schedule
documentation: ug
keywords: context-menu
---
# Context Menu

Scheduler provides default context menu options for both appointments as well as work cells. It also allows to define additional custom context menu options.

The options that are available under `ContextMenuSettings` are as follows,

* **Enable** - Enables/disables the context menu option in Scheduler.
* **MenuItems** - Contains the sub-menu collections related to both the appointment and cells.

## Default Menu Options

The menu items contains two separate collection based on the appointment and cells. 

### Appointment

The appointment collection includes the following options. 

<table>
<tr>
<td>
Open Appointment (default)</td></tr>
<tr>
<td>
Delete Appointment (default)</td></tr>
<tr>
<td>
Print Appointment</td></tr>
<tr>
<td>
Categorize</td></tr>
</table>

### Cells

The default options available within the cell collection includes - 

<table>
<tr>
<td>
New Appointment</td></tr>
<tr>
<td>
New Recurring Appointment</td></tr>
<tr>
<td>
Today</td></tr>
<tr>
<td>
Go to date</td></tr>
<tr>
<td>
Settings (View, TimeMode, Work Hours) </td></tr>
</table>
The following code snippet shows how to enable the context menu settings in Scheduler and to make use of it with default available options. 

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
            </AppointmentCollection>
            <CellsCollection>
                <ej:Cells Id="new" Text="New Appointment" />
                <ej:Cells Id="recurrence" Text="New recuring Appointment" />
                <ej:Cells Id="today" Text="Today" />
                <ej:Cells Id="gotodate" Text="Go to Date" />
                <ej:Cells Id="settings" Text="Settings"/>
                <ej:Cells Id="view" Text="view" ParentId="settings"/>
                <ej:Cells Id="timemode" Text="Time Mode" ParentId="settings"/>
                <ej:Cells Id="view_Day" Text="Day" ParentId="view"/>
                <ej:Cells Id="view_Week" Text="Week" ParentId="view"/>
                <ej:Cells Id="view_Workweek" Text="Workweek" ParentId="view"/>
                <ej:Cells Id="view_Month" Text="Month" ParentId="view"/>
                <ej:Cells Id="timemode_Hour12" Text="12 Hours" ParentId="timemode"/>
                <ej:Cells Id="timemode_Hour24" Text="24 Hours" ParentId="timemode"/>
                <ej:Cells Id="workhours" Text="Work Hours" ParentId="settings"/>
            </CellsCollection>
        </MenuItems>
    </ContextMenuSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>  
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
         SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> In agenda view, only the appointment menu items shows up in the context menu options. For default menu items, the Id must be defined the same as mentioned in the above code example – as we have processed the menus based on this Id within our source.


## Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu of both the appointment and cell collection.

The following code example depicts how **to add the custom menu items** to the appointment and cell collection of the context menu settings.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
                <ej:Appointment Id="option1" Text="User Option 1" />
            </AppointmentCollection>
            <CellsCollection>
                <ej:Cells Id="celloption1" Text="Custom Option 1" />
            </CellsCollection>
        </MenuItems>
    </ContextMenuSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>  
</ej:Schedule>

 <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> The **Id** given for the custom menu items **must be unique** in both the appointment and cell collection.  

## Handling Menu Actions

To define specific actions for a click made on the custom menu items, the client-side event `menuItemClick` can be used as depicted in the below code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" MenuItemClick="onMenuItemClick">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
                <ej:Appointment Id="option1" Text="User Option 1" />
            </AppointmentCollection>
        </MenuItems>
    </ContextMenuSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>  
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
           
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onMenuItemClick(args) {
            //args.events contains information of the clicked menu item.
            if (args.events.ID == "option1")
                alert("Custom menu clicked");
        }
    </script>
</asp:Content>

{% endhighlight %}

Also, it is possible to predict the target on which the right click is made, either on the cells or appointments with the use of the event `beforeContextMenuOpen`. The below code example shows how to block the display of context menu, when right clicked on the cells by setting **args.cancel** as **true**.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" BeforeContextMenuOpen="onBeforeContextMenuOpen">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
                <ej:Appointment Id="option1" Text="User Option 1" />
            </AppointmentCollection>
        </MenuItems>
    </ContextMenuSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>  
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onBeforeContextMenuOpen(args) {
            //args.events.target – target information to depict either cell/appointment
            if ($(args.events.target).hasClass("e-workcells") || $(args.events.target).hasClass("e-monthcells"))
                args.cancel = true;
        }
    </script>
</asp:Content>

{% endhighlight %}

## Adding Categorize Option

To include the default categorize option within the context menu, it is necessary to enable the `CategorizeSettings` property as shown in the below code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
                <ej:Appointment Id="categorize" Text="Categorize" />
            </AppointmentCollection>
        </MenuItems>
    </ContextMenuSettings>
    <CategorizeSettings Enable="true"></CategorizeSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>  
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> The **Categorize** option must be added only to the **Appointment** collection, which displays on right clicking the appointments.

