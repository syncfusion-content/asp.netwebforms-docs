---
title: Working with appointments
description: Working with Scheduler appointments and its related options like Recurrence.
platform: aspnet
control: schedule
documentation: ug
keywords: appointments, appointment, recurrence, recurring appoitnment, all day 
---
# Working with Appointments

An appointment represents a certain time interval in a schedule cell depicting a plan made for the specified time interval. 

## Appointment Types

The types of appointments available within Scheduler can be categorized as follows 

### Normal 

Represents an appointment that is created for a certain time interval on a single or more number of days. If the normal appointment is created for more than 24 hours, then those longer appointments will be rendered on the all-day row.

N> If the normal appointment is to be created for two days (say from November 25, 2015 – 11.00 PM to November 26, 2015 2.00 AM) but less than 24 hour time interval, then the appointment is split into two parts and will be displayed appropriately on both the days.

### All-Day 

Represents an appointment that is created for an entire day such as holiday events. It renders separately in an All-day cell, a separate place for all-day appointments. In Timeline (horizontal) view, all-day appointment renders in the usual work cells, as no all-day cells are present in that view. 

N> An all-day row is normally visible on the Scheduler, as the `ShowAllDayRow` property is set to true by default. 

### Recurrence

Represents an appointment that is created for a certain time interval that occurs repeatedly in a daily, weekly, monthly or yearly basis at the same time interval based on the Recurrence rule. The other available options and validations that can be performed on recurrence appointments can be referred from [here](/aspnet/schedule/working-with-appointments#recurrence-options).

## CRUD operation 

Appointments play a dynamic role within the Schedule control with which the users mostly interact. You can manipulate (add/edit/delete/drag/resize) the required appointments that reveals one of the main purpose of the Schedule control.

### Add/Edit Appointments

The appointments can be added/edited in the Scheduler using any one of the following ways,

* Quick window
* Default appointment window
* [Context menu](/aspnet/schedule/context-menu)
* Through programmatically

#### Quick Window


The Quick window usually pops out while single clicking on the Scheduler cells or appointments. It requires the user to enter the Subject to proceed with the appointment creation. It also includes an **Edit** **Appointment** option displayed at the bottom left corner – on selection which opens up the normal appointment window.

On single clicking the scheduler appointments, the pop-up that shows up contains the appointment information along with the other options that are listed below,

* Edit Appointment
* Edit Series (only for the recurrence appointments)
* Delete icon

The quick window option can be enabled/disabled by using `ShowQuickWindow` API, whereas its default value is set to **true**.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" ShowQuickWindow="false" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> Select multiple cells either using mouse or keyboard access keys (<kbd>shift</kbd>+<kbd>arrow keys</kbd>) and press <kbd>enter</kbd> key, so that the quick window opens up for the selected date/time range.

Another way to disable the quick window option at dynamic time can be achieved through the `CellClick` and `AppointmentClick` events. The below code example shows the way to disable the quick appointment window only while clicking on the cells, but displays for appointments.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" ShowQuickWindow="true" CurrentDate="5/2/2014" CellClick="onCellClick">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onCellClick(args) {
            args.cancel = true;// Prevents the display of quick window on clicking the cells.
        }
    </script>
</asp:Content>

{% endhighlight %}


#### Default Appointment Window

The default appointment window is availed with options like 

* Subject
* Start and End Time
* All-Day
* TimeZone (for both Start and End time)
* Repeat options
* Description

The other additional options available are listed below for which the appropriate API’s are needed to be configured to display these options on the appointment window.

* Location 
* Priority 
* Categorize 
* Resources   

The appointments can be created by double-clicking on the Scheduler cells across the required time slots, which makes the create Appointment window to pop-up. The start and end time will gets automatically populated, according to the time-slot selection. Clicking on the done button in an appointment window will create the appointment for the selected time cells.

N> Select multiple cells both using mouse or keyboard access keys (<kbd>shift</kbd>+<kbd>arrow keys</kbd>) and press <kbd>Alt</kbd>+<kbd>N</kbd> key, so that the default appointment window opens up for the selected date/time range with the Start and End time fields automatically filled in.

To prevent the display of default appointment window on double clicking the Scheduler cells, either the `AppointmentWindowOpen` or `CellDoubleClick` event can be used, within which the **args.cancel** needs to be set to true. This behavior is depicted in the below code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData"  CurrentDate="5/2/2014" AppointmentWindowOpen="onAppointmentWindowOpen">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onAppointmentWindowOpen(args) {
            args.cancel = true;// Prevents the display of quick window on clicking the cells.
        }
    </script>
</asp:Content>

{% endhighlight %}

#### Through Programmatically

You can add/edit the appointments dynamically through the public method `saveAppointment`. It accepts the JSON Object data (either a new or updated appointment object) as its argument.

{% highlight html %}

<button id="btnAdd" value="Add" type="submit" onclick="addAppointment()">Add</button>

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData"  CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        //addAppointment is a function, gets called on clicking the Add button
        function addAppointment() {
            //appointment details 
            var appointment = {
                Subject: "Gym",
                StartTime: new Date("2014/5/2 03:30 AM"),
                EndTime: new Date("2014/5/2 04:30 AM")
            };

            //create the schedule object 
            var schObj = $("#Schedule1").data("ejSchedule");
            //pass the JSON object in the public method 
            schObj.saveAppointment(appointment);
        }
    </script>
</asp:Content>

{% endhighlight %}

### Delete Appointments

The appointments can be deleted using either of the following ways,

* Selecting an appointment and clicking on the delete icon in the quick appointment window.
* Hovering the mouse over appointments and clicking on Inline delete option which is enabled by default for all the appointments.
* Selecting an appointment and pressing <kbd>Delete</kbd> key.
* Through Programmatically.

A pop-up with a confirmation message will get displayed before deleting an appointment, which can be customized as mentioned [here](/aspnet/schedule/globalization-and-localization#localization:localizing-specific-words).

**For example**, to localize only the delete confirmation message in the delete window - 

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData"  CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        var deleteCustomizationMessage = {
            // customize the confirmation message
            DeleteConfirmation: "Do you want to delete this Event?",
            // customize the delete window title
            MouseOverDeleteTitle: "Delete Event",
            // customize the recurrence delete window title
            RecurrenceDeleteTitle: "Delete Repeat Event"
        };

        // Extend only the required changes to the original locale collection
        $.extend(ej.Schedule.Locale["en-US"], deleteCustomizationMessage);

    </script>
</asp:Content>

{% endhighlight %}

N> All these CRUD operations on appointments (add/edit/delete) can also be done through the default [context menu](/aspnet/schedule/context-menu#default-menu-options) options **Add Appointment**, **Edit Appointment** and **Delete Appointment** which is available, when context menu settings is enabled within Scheduler.

#### Through Programmatically

You can delete the appointments dynamically through the public method `deleteAppointment`, which accepts the Guid of the appointment or complete appointment data as its argument. The Guid is availed as one of the appointment element’s attribute.

For example, here the below code example depicts the way to delete the appointments programmatically by calling the **deleteAppointment** function within the `AppointmentClick event, which triggers whenever the user clicks on an appointment.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData"  CurrentDate="5/2/2014" AppointmentClick="onAppointmentClick">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        //addAppointment is a function, gets called on clicking the Add button
        function onAppointmentClick(args) {
            var schObj = $("#Schedule1").data("ejSchedule");
            schObj.deleteAppointment(args.appointment.Guid);
            // $($(".e-appointment")[0]).attr("guid") --> To get the guid attribute value of an element directly.
        }
    </script>
</asp:Content>

{% endhighlight %}

## Handling Appointment Actions

It is possible to define some specific actions to take place after the CRUD operation occurs on the Scheduler appointments through the following available client-side events,

* BeforeAppointmentCreate
* BeforeAppointmentChange
* BeforeAppointmentRemove

**BeforeAppointmentCreate** – Triggers before saving a new appointment.

**BeforeAppointmentChange** – Triggers when an appointment is edited and before it is being updated to the dataSource.

**BeforeAppointmentRemove** – Triggers before deleting an existing appointment.

To stop the save, edit and delete actions on the Scheduler appointments, following code example can be used.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData"  CurrentDate="5/2/2014" BeforeAppointmentCreate="onAppointmentSave" BeforeAppointmentChange="onAppointmentEdit" BeforeAppointmentRemove="onAppointmentDelete">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onAppointmentSave(args) {
            args.cancel = true; // cancels the save action on appointments.
        }

        function onAppointmentEdit(args) {
            args.cancel = true; // cancels the edit action on appointments.
        }

        function onAppointmentDelete(args) {
            args.cancel = true; // cancels the delete action on appointments.
        }
    </script>
</asp:Content>

{% endhighlight %}

## Read Only

An interaction with the appointments of the Scheduler can be enabled/disabled through the `ReadOnly` property. When the `ReadOnly` property is set to `true`, it is not possible to do any actions on the appointments, but you can navigate between the schedule dates, views and can also be able to see the appointment details in the quick window. By default, this property is set to `false`.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" ReadOnly="true" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> When the `ReadOnly` property is set to true – double clicking the cells will open the appointment window filled with appointment details, which can be allowed to view but cannot be edited or saved.

## Drag and Drop

The appointment time can be modified through the drag and drop behavior, by dragging and dropping it to the new location, so that the start time and end time of the appointment gets changed automatically. We can enable/disable the drag and drop functionality through the `AllowDragAndDrop` property. By default, it is set to `true`.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" AllowDragAndDrop="false" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

### Handling Drag Actions Dynamically

The drag and drop functionality can be handled with the following three events,

* DragStart
* Drag
* DragStop

**DragStart** – Triggers when the appointments are started to drag from its source location.

**Drag** – Triggers when the appointments are being dragged over.

**DragStop** – Triggers when the appointments are dropped on a destined location.

The following code example shows how to cancel the dragging functionality with the help of one of these events.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" DragStop="onDragStop" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onDragStop(args) {
            args.cancel = true; // cancels the drag action on appointments.
        }
    </script>
</asp:Content>

{% endhighlight %}

### External Drag and Drop

It is possible to drag and drop the external items to and fro the Scheduler control. This action is handled through the property `AppointmentDragArea` 
which specifies the draggable area name stating whether the appointments can be dragged outside of the control or within it.

The following code example lets you drag and drop the external items from the tree view control to the Scheduler.

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">
    <div class="row">
         <div class="col-xs-4 col-sm-2" style="float:left">
              <span class=""><b>Tutorials </b> </span>
                <ej:TreeView ID="treeview" runat="server" Height="100%" AllowDragAndDrop="true" AllowDropChild="false" AllowDropSibling="false" AllowDragAndDropAcrossControl="true" ClientSideOnNodeDropped="onNodeDropped" ClientSideOnNodeDragStarted="onNodeDrag">
                    <Nodes>
                        <ej:TreeViewNode Expanded="True" Text="HTML">
                            <Nodes>
                                 <ej:TreeViewNode Text="Introduction"></ej:TreeViewNode>
                                 <ej:TreeViewNode Text="Editors"></ej:TreeViewNode>
                                 <ej:TreeViewNode Text="Styles"></ej:TreeViewNode>
                                 <ej:TreeViewNode Text="Formatting"></ej:TreeViewNode>
                                 <ej:TreeViewNode Text="Tables"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeView>
          </div>

          <div style="float:left" class="col-xs-18 col-sm-9">
               <span class=""><b> Training Scheduler Panel</b> <br></span>
								<i>Note</i>: To Schedule classes, drag the topics from <b>Tutorials</b> and drop it over <b>Training Scheduler Panel</b>
            <ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CellWidth="40px" CurrentDate="5/5/2014" Views="Day,Week,WorkWeek,Month" ShowCurrentTimeIndicator="false" EnableRecurrenceValidation="false" AppointmentDragArea="body" DragStop="onDragStop">
                <Group Resources="Owners" />
                    <Resources>
                    <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
                    <ResourceSettings Color="color" Id="id" Text="text">
                </ResourceSettings>
            </ej:Resources>
        </Resources>
         <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
        </ej:Schedule>
      </div>

    </div>
    <div id="customWindow" style="display: none">
        <div id="custom">
            <table width="100%" cellpadding="5">
                <tbody>
                    <tr>
                        <td>
                            Subject:
                        </td>
                        <td colspan="2">
                            <input id="subject" type="text" value="" name="Subject" style="width: 100%" readonly />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Description:
                        </td>
                        <td colspan="2">
                            <textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            StartTime:
                        </td>
                        <td>
                            <input id="StartTime" type="text" value="" name="StartTime" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            EndTime:
                        </td>
                        <td>
                            <input id="EndTime" type="text" value="" name="EndTime" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Resource:
                        </td>
                        <td colspan="2">
                            <input id="resource" type="text" value="" name="Resource" style="width: 100%" readonly/>
                        </td>
                    </tr>
                    <tr style="display: none">
                        <td>
                            ownerId:
                        </td>
                        <td colspan="2">
                            <input id="ownerId" type="text" name="ownerId" />
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div>
            <button type="submit" onclick="cancel()" id="btncancel" style="float:right;margin-right:20px;margin-bottom:10px;">Cancel</button>
            <button type="submit" onclick="save()" id="btnsubmit" style="float:right;margin-right:20px;margin-bottom:10px;">Save</button>
        </div>
    </div>

     <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>
</asp:Content>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        $(function () {
            $("#customWindow").ejDialog({
                width: 600,
                height: "auto",
                position: { X: 400, Y: 200 },
                showOnInit: false,
                enableModal: true,
                title: "Create Appointment",
                enableResize: false,
                allowKeyboardNavigation: false,
                close: "clearFields",

            });
            $("#btncancel").ejButton({ width: '85px' });
            $("#btnsubmit").ejButton({ width: '85px' });
        });
        function onNodeDrag(e) {
            if (e.targetElementData.parentId == "") return false;
        }
        function onNodeDropped(e) {
            if ($(e.target).parents(".e-schedule").length != 0) {
                var scheduleObj = $("#Schedule1").data("ejSchedule");
                var index = $($(e.target).context).hasClass("e-workcells") || $($(e.target).context).hasClass("e-alldaycells") ? $($(e.target).context).index() : $($(e.target).context).hasClass("e-alldaycells") ? $($(e.target).context).index() : 7 - ((parseInt($($(e.target).context).index() / 7) + 1) * 7 - $($(e.target).context).index()) + ($($(e.target).context).parent().index() * 7);
                if (scheduleObj.model.orientation == "horizontal") {
                    index = scheduleObj.model.showTimeScale ? scheduleObj.currentView() !== "month" && !(scheduleObj._isCustomView()) ? Math.floor(index / ((scheduleObj.model.endHour - scheduleObj.model.startHour) * 2)) : index : $(e.event.target).index();

                }
                var renderDate = (scheduleObj.model.orientation == "horizontal" && scheduleObj.currentView() == "month") ? scheduleObj.monthDays : scheduleObj.model.orientation == "vertical" ? scheduleObj.dateRender : scheduleObj._dateRender;
                renderDate = scheduleObj.model.orientation == "horizontal" && scheduleObj.currentView() == "customview" && scheduleObj._dateRender.length <= 7 ? scheduleObj._dateRender : renderDate;
                var curDate = new Date(renderDate[index]);

                var _target = $($(e.target).context);
                if ($(_target).hasClass("e-workcells") && (scheduleObj.model.showTimeScale) && scheduleObj.currentView() !== "month" && !(scheduleObj._isCustomView())) {
                    var time = scheduleObj.model.orientation == "vertical" ? scheduleObj.model.startHour + ($(e.event.target).parent().index() / 2) : scheduleObj.model.startHour + (($(e.event.target).index() - (((scheduleObj.model.endHour - scheduleObj.model.startHour) * 2) * index)) / 2);
                    var timemin = time.toString().split(".");
                    var cur_StartTime = new Date(curDate).setHours(parseInt(timemin[0]), parseInt(timemin[1]) == 5 ? 30 : 00);
                    var min = (parseInt(new Date(cur_StartTime).getHours()) == 23 && parseInt(new Date(cur_StartTime).getMinutes()) == 30) ? new Date(cur_StartTime).getMinutes() + 29 : new Date(cur_StartTime).getMinutes() + 30;
                    var cur_EndTime = new Date(new Date(cur_StartTime).setMinutes(min));
                }
                else if ($(_target).hasClass("e-workcells") && scheduleObj.model.orientation == "horizontal" && scheduleObj.currentView() == "month") {
                    var cur_StartTime = new Date(new Date(curDate).setHours(0, 0));
                    var cur_EndTime = new Date(new Date(curDate).setHours(23, 59));
                }
                else {
                    var cur_StartTime = new Date(new Date(curDate).setHours(0, 0));
                    var cur_EndTime = new Date(new Date(curDate).setHours(23, 59));
                    scheduleObj._appointmentAddWindow.find(".allday").ejCheckBox({ checked: true });
                }

                var StartDate = new Date(cur_StartTime);
                var StartTime = new Date(cur_StartTime);
                var endTime = cur_EndTime;

                // To find the resource details               
                var resource = scheduleObj._getResourceValue($($(e.target).context));

                // custom appointmnt window 

                $("#subject").val(e.droppedElementData.text);
                $("#customdescription").val(e.droppedElementData.text);
                $("#StartTime").ejDateTimePicker({ value: new Date(StartTime) });
                $("#EndTime").ejDateTimePicker({ value: new Date(endTime) });
                $("#resource").val(resource.text);
                $("#ownerId").val(resource.id);
                $("#customWindow").ejDialog("open");
            }
        }
        function save() {
            var obj = {};
            obj["Subject"] = $("#subject")[0].value;
            obj["Description"] = $("#customdescription")[0].value;
            obj["StartTime"] = new Date($("#StartTime")[0].value);
            obj["EndTime"] = new Date($("#EndTime")[0].value);
            obj["OwnerId"] = $("#ownerId")[0].value;
            $("#customWindow").ejDialog("close");
            var object = $("#Schedule1").data("ejSchedule");
            object.saveAppointment(obj);
        }

        function cancel() {
            $("#customWindow").ejDialog("close");
        }

        function onDragStop(args) {
            if ($(args.event.target).parents(".e-treeview").length != 0) {
                $("#treeview").ejTreeView({ allowDropChild: true, allowDropSibling: true });
                treeObj = $("#treeview").ejTreeView('instance');
                var newNode = { id: args.appointment.Id, text: args.appointment.Subject };
                treeObj.addNode(newNode, $(args.event.target));
                args.cancel = true;
            }
        }
    </script>
</asp:content>

<asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection">
    <style type="text/css">
        #custom table td{
			padding:5px;
		}
        .e-icon.e-minus:before {
		content: "\e676";
		}
     </style>
</asp:Content>

{% endhighlight %} 

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class ExternalDragAndDrop : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Rooms> owners = new List<Rooms>();
            owners.Add(new Rooms { text = "Nancy", id = "1", color = "#f8a398" });
            owners.Add(new Rooms { text = "Steven", id = "3", color = "#56ca85" });
            owners.Add(new Rooms { text = "Michael", id = "5", color = "#51a0ed" });
            Schedule1.Resources[0].ResourceSettings.DataSource = owners;
        }
        public class Rooms
        {
            public string text { set; get; }
            public string id { set; get; }
            public string groupId { set; get; }
            public string color { set; get; }
        }
    }
}

{% endhighlight %}

## Resize

Resizing an appointment is another way to change its start or end time. Mouse hover on the appointments, so that the resizing handlers gets displayed on either sides of the appointment which allows resizing. The resizing functionality can be enabled/disabled by setting the `EnableAppointmentResize` property. By default it is set to `true`.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" EnableAppointmentResize="false" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

### Handling Resize Actions Dynamically

The appointment resizing functionality can be handled through the following three events,

* ResizeStart
* Resize
* ResizeStop

**ResizeStart** – Triggers when the appointments are started resizing from its original time.

**Resize** – Triggers when the appointment resizing is in progress.

**ResizeStop** – Triggers when the appointment resizing is done.

The following code example shows how to cancel the resizing functionality with the help of one of these events.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" ResizeStart="onResizeStart" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onResizeStart(args) {
            args.cancel = true; // Blocks the resize action on appointments.
        }
    </script>
</asp:Content>

{% endhighlight %}

## Categorization

It allows to differentiate the appointments with various categorize options and individual colors. You can also denote the status of the appointments using this categorize option and can specify your own user-defined category collection. It is also possible to select multiple categorize for a single appointment.

### Categorize Settings

The `CategorizeSettings` is an object collection that holds below categorize related properties such as,

* `Enable` - It accepts true or false value, denoting whether to enable/disable the categorize option. Its default value is `false`.
* `AllowMultiple` – It enables or disables the multiple selection of categories for each appointments in the appointment window as well as in the context menu. Its default value is `false`.
* `DataSource` – Bind the categorize collection. This property should be assigned with the List data collection or [DataManger](/aspnet/datamanager/overview). We have below 6 default values for data source collection.

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class CategorizeOption : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Categorize> CategorizeValue = new List<Categorize>();

            CategorizeValue.Add(new Categorize { text = "Blue Category", id = 1,   color ="#43b496", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Green Category", id = 2,  color ="#7f993e", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Orange Category", id = 3, color ="#cc8638", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Purple Category", id = 4, color ="#ab54a0", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Red Category", id = 5,    color ="#dd654e", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Yellow Category", id = 6, color ="#d0af2b", fontColor= "#ffffff" });

            Schedule1.CategorizeSettings.DataSource = CategorizeValue;
        }
        public class Categorize
        {
            public string text { set; get; }
            public int id { set; get; }
            public string fontColor { set; get; }
            public string color { set; get; }
        }
    }
}

{% endhighlight %}

The below categorize fields holds the appropriate column names from the dataSource - 

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Id<br/><br/></td><td>
It holds the binding name for <b>Id</b> field in the categorize dataSource<br/><br/></td></tr>
<tr>
<td>
Text<br/><br/></td><td>
It holds the binding name for <b>Text</b> field in the categorize dataSource<br/><br/></td></tr>
<tr>
<td>
Color<br/><br/></td><td>
It holds the binding name for <b>Color</b> field in the categorize dataSource.<br/><br/></td></tr>
<tr>
<td>
FontColor<br/><br/></td><td>
It holds the binding name for <b>Fontcolor</b> field in the categorize dataSource. This font color apply in the appointment.<br/><br/></td></tr>
</table>

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule  ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014">
    <CategorizeSettings Enable="true" AllowMultiple="true" Id="id" Color="color" FontColor="fontColor" Text="text">
    </CategorizeSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Categorize="Categorize"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class CategorizeOption : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Categorize> CategorizeValue = new List<Categorize>();

            CategorizeValue.Add(new Categorize { text = "Blue Category", id = 1,   color ="#43b496", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Green Category", id = 2,  color ="#7f993e", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Orange Category", id = 3, color ="#cc8638", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Purple Category", id = 4, color ="#ab54a0", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Red Category", id = 5,    color ="#dd654e", fontColor= "#ffffff" });
            CategorizeValue.Add(new Categorize { text = "Yellow Category", id = 6, color ="#d0af2b", fontColor= "#ffffff" });

            Schedule1.CategorizeSettings.DataSource = CategorizeValue;
        }
        public class Categorize
        {
            public string text { set; get; }
            public int id { set; get; }
            public string fontColor { set; get; }
            public string color { set; get; }
        }
    }
}

{% endhighlight %}

## Priority

This option prioritize the appointments based on its importance and it can be differentiated with each individual icons/images. By default, there are some specific set of default priority collection and you can also customize it with your own priority collection.

### Priority Settings

The `PrioritySettings` is an object collection that holds the below priority related properties such as,

* `Enable` - It accepts true or false value, denoting whether to enable/disable the priority option. Its default value is **false**.
* `Template` – Customize the priority icon/images using template options. Refer this [priority template](/aspnet/schedule/templates#priority-settings-template) topic.
* `DataSource` – binds the priority collection. This property should be assigned with the list data collection or [DataManger](/aspnet/datamanager/overview). We have below 4 default values for priority data source collection.

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class Default : System.Web.UI.Page
    {
        List<Priority> priority = new List<Priority>();
        protected void Page_Load(object sender, EventArgs e)
        {
            priority.Add(new Priority { text = "None", value = "none" });
            priority.Add(new Priority { text = "High", value = "high" });
            priority.Add(new Priority { text = "Medium", value = "medium" });
            priority.Add(new Priority { text = "Low", value = "low" });
            Schedule1.PrioritySettings.DataSource = priority;
        }
        public class Priority
        {
            public string text { get; set; }
            public string value { get; set; }
        }
    }
}

{% endhighlight %}

The below priority fields holds the appropriate column names from the dataSource,

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Text<br/><br/></td><td>
It holds the binding name for <b>Text</b> field in the priority dataSource<br/><br/></td></tr>
<tr>
<td>
Value<br/><br/></td><td>
It holds the binding name for <b>Value</b> field in the priority dataSource.<br/><br/></td></tr>
</table>

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
   <PrioritySettings Enable="true" Text="text" Value="value"></PrioritySettings>
     <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Priority="Priority" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class Default : System.Web.UI.Page
    {
        List<Priority> priority = new List<Priority>();
        protected void Page_Load(object sender, EventArgs e)
        {
            priority.Add(new Priority { text = "None", value = "none" });
            priority.Add(new Priority { text = "High", value = "high" });
            priority.Add(new Priority { text = "Medium", value = "medium" });
            priority.Add(new Priority { text = "Low", value = "low" });
            Schedule1.PrioritySettings.DataSource = priority;
        }
        public class Priority
        {
            public string text { get; set; }
            public string value { get; set; }
        }
    }
}

{% endhighlight %}

## Search or Filter Appointments

### Appointment Search

The public method `searchAppointments` is used to search the appointments in the scheduler dataSource. It contains below four arguments such as search string, search field, filter operator and ignorecase.

**searchString** - It is used to search the given word / sentence with in the appointments data.

**fields** - It is the field, with which the search operation takes place. It’s an optional argument.

**filterOperator** – It contains the filter type like contains, greater than or less than. It’s an optional argument.

**ignoreCase** – It is a boolean value to set the search string as case sensitive or not. It’s an optional argument.

{% highlight html %}

<input id="txtSearch" type="text" />
<input id="btnSearch" onclick="search()" type="button" value="Search" />
<div id="grid1" /> 

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function search(){
            var _searchString = $("#txtSearch").val();
            var schObj = $("#Schedule1").data("ejSchedule");
            // method to retrieve the appointment based on search string
            var result = schObj.searchAppointments(_searchString);
            showResult(result, _searchString);
        }

        // method to show the result in a grid
        function showResult(list, _searchString) {
            if (!ej.isNullOrUndefined(list) && list.length != 0 && _searchString != "") {
                $("#grid1").show();
                $("#grid1").data("ejGrid") && $("#grid1").ejGrid("destroy");
                $("#grid1").ejGrid({
                    allowScrolling: true,
                    dataSource: list,
                    allowPaging: true
                });
            }
        }
    </script>
</asp:Content>

{% endhighlight %}

### Appointment Filters

The appointments can be filtered or shortlisted based on the simple or complex conditions with four available properties such as **field**, **operator**, **value** and **predicate** which is passed to the public method `filterAppointments`.

**field** - It is the field, with which the search operation takes place. It’s an optional argument.

**operator** – It is generally used to specify the [filter](/aspnet/datamanager/filtering) type. 

**value** – It is the filter keyword based on which the records are filtered.

**predicate** – Add more than one condition query using **and**, **or** [predicate](/aspnet/datamanager/filtering#and-predicate).

{% highlight html %}

<input id="btnSearch" onclick="search()" type="button" value="Search" />
    <div id="grid1" /> 
<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function search(){
            // Add the filter data as like in the below format
            var filter = [{
                field: "Subject", // field configure
                operator: "contains",
                value: "MayDay",
                predicate: "or" // predicate 
            }, {
                field: "Subject", // field configure
                operator: "contains",
                value: "Daily Planet",
                predicate: "or" // predicate
            }];

            var schObj = $("#Schedule1").data("ejSchedule");
            // Method to get the Filtered appointment
            var result = schObj.filterAppointments(filter);
            showResult(result);
        }

        // method to show the result in a grid
        function showResult(list, _searchString) {
            if (!ej.isNullOrUndefined(list) && list.length != 0 && _searchString != "") {
                $("#grid1").show();
                $("#grid1").data("ejGrid") && $("#grid1").ejGrid("destroy");
                $("#grid1").ejGrid({
                    allowScrolling: true,
                    dataSource: list,
                    allowPaging: true
                });
            }
        }
    </script>
</asp:Content>

{% endhighlight %}


## Recurrence Options

There are scenarios where you require the same appointments to be repeatedly created for multiple days on daily, weekly, monthly, and yearly or every weekday basis. 

In appointment data collection, **recurrence** and **recurrenceRule** are depended fields. While creating or binding the recurrence appointment, the **recurrence** field is set to **true** and **recurrenceRule** contains recurrence pattern details in string format.

### Recurrence Rule

The recurrence appointments are created based on the recurrence rule. The RecurrenceRule is a string value that contains the details of the recurrence appointments like 

* repeat type - daily/weekly/monthly/yearly 
* how many times it needs to be repeated 
* the interval duration
* the time period to render the appointment, etc.,

It has the following properties based on which the recurrence appointments are rendered in the Schedule control with its respective time period.

<table>
<tr>
<th>
S.No<br/><br/></th><th>
Property<br/><br/></th><th>
Purpose<br/><br/></th></tr>
<tr>
<td>
1<br/><br/></td><td>
FREQ<br/><br/></td><td>
Maintains the Repeat type value of the appointment. <br/><br/>(<b>Example</b>: Daily, Weekly, Monthly, Yearly, Every week day)<br/><br/>Example: <b>FREQ=DAILY</b>;INTERVAL=1<br/><br/></td></tr>
<tr>
<td>
2<br/><br/></td><td>
INTERVAL<br/><br/></td><td>
Maintains the interval value of the appointments.<br/><br/><b>For example</b>, when you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday. (Creates an appointment on all days by leaving the interval of one day gap)<br/><br/>Example: FREQ=DAILY;<b>INTERVAL=2</b><br/><br/></td></tr>
<tr>
<td>
3<br/><br/></td><td>
COUNT<br/><br/></td><td>
It holds the appointment’s count value. <br/><br/><b>For example</b>, When the recurrence appointment count value is 10, which means that 10 instances of appointments are created in the recurrence series.<br/><br/>Example: FREQ=DAILY;INTERVAL=1;<b>COUNT=10</b><br/><br/></td></tr>
<tr>
<td>
4<br/><br/></td><td>
UNTIL<br/><br/></td><td>
This property is used to store the recurrence end date value. <br/><br/><b>For example</b>, when you set the end date of appointment as 11/30/2015, the UNTIL property holds the end date value denoting when the recurrence actually ends.<br/><br/>Example: FREQ=DAILY;INTERVAL=1;<b>UNTIL=11/30/2015</b><br/><br/></td></tr>
<tr>
<td>
5<br/><br/></td><td>
BYDAY<br/><br/></td><td>
It holds the <b>DAY</b> values, representing on which the appointments actually renders. <br/><br/><b>For example</b>, Create the weekly appointment, and select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday). When Monday is selected, the first two letters of the selected day “MO” is saved in the <b>BYDAY</b> property. When multiple days are selected, the values are separated by commas.<br/><br/>Example: FREQ=WEEKLY;INTERVAL=1;<b>BYDAY=MO,WE</b>;COUNT=10<br/><br/></td></tr>
<tr>
<td>
6<br/><br/></td><td>
BYMONTHDAY<br/><br/></td><td>
This property is used to store the date value of the Month, while creating the Month recurrence appointment.<br/><br/><b>For example</b>, when you create a Monthly recurrence appointment for every 3rd day of the month, then <b>BYMONTHDAY</b> holds the value 3 and creates the appointment on 3rd day of every month.<br/><br/>Example: FREQ=MONTHLY;<b>BYMONTHDAY=3</b>;INTERVAL=1;COUNT=10<br/><br/></td></tr>
<tr>
<td>
7<br/><br/></td><td>
BYMONTH<br/><br/></td><td>
This property is used to store the index value of the selected Month while creating the yearly appointments.<br/><br/><b>For example</b>, when you create the yearly appointment on June month, the index value of June month 6 will get stored in the BYMONTH field. The appointment is created on every 6th month of a year.<br/><br/>Example: FREQ=YEARLY;BYMONTHDAY=16;<b>BYMONTH=6</b>;INTERVAL=1;COUNT=10<br/><br/></td></tr>
<tr>
<td>
8<br/><br/></td><td>
BYSETPOS<br/><br/></td><td>
This property is used to store the index value of the week. <br/><br/><b>For example</b>, when you create the monthly appointment in second week of a month, the index value of the second week (2) is stored in BYSETPOS.<br/><br/>Example: FREQ=MONTHLY;BYDAY=MO;<b>BYSETPOS=2</b>;UNTIL=8/11/2015<br/><br/></td></tr>
<tr>
<td>
9<br/><br/></td><td>
WKST<br/><br/></td><td>
This property is used to store the start day value of a week.<br/><br/><b>For example</b>, when you render the workweek the “WKST” value is Monday.<br/><br/></td></tr>
<tr>
<td>
10 <br/><br/></td><td>
EXDATE<br/><br/></td><td>
EXDATE is used to hold the modified appointment date details (date value) in the recurrence appointment series.<br/><br/><b>For example</b>, when you change the recurrence appointment instance under the date “6/19/2015”, then this date is added to the recurrence rule EXDATE field. “EXDATE” is also used to differentiate the edited occurrence of the recurrence series for some internal process while doing the “Edit Series or Delete series” actions.<br/><br/>Example: FREQ=WEEKLY;BYDAY=MO,TU,WE,TH,FR;COUNT=10;<b>EXDATE=6/18/2015,6/20/2015</b>;RECUREDITID=1651<br/><br/></td></tr>
<tr>
<td>
11<br/><br/></td><td>
RECUREDITID<br/><br/></td><td>
This property contains the Parent Id value of the edited appointment. It is used to track the edited appointment occurrence with its parent recurrence appointment series.<br/><br/><b>For example</b>, when you edit the particular occurrence of the recurrence appointment series, the “RECUREDITID” is added to that edited appointment depicting its parent Id.<br/><br/>Example:<br/><br/>FREQ=WEEKLY;BYDAY=MO,TU,WE,TH,FR;COUNT=10;EXDATE=6/18/2015,6/20/2015;<b>RECUREDITID=1651</b><br/><br/></td></tr>
</table>
To know more about other possible combinations of above specified recurrence rule properties, refer [here](http://www.syncfusion.com/kb/3719/what-is-recurrencerule-in-the-schedule-control).

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
    <AppointmentSettings Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

### Recurrence Validation

The default recurrence validation has been included for recurrence appointments similar to the one available in outlook. The validation occurs during the recurrence appointment creation, drag and drop of the recurrence appointments and also if any single occurrence changes. The validation can be disabled by setting the `EnableRecurrenceValidation` to `false`.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" EnableRecurrenceValidation="false" CurrentDate="5/2/2014">
    <AppointmentSettings Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> You can parse the **RecurrenceRule** of an appointment from the server-side by making use of a new generic utility class **RecurrenceHelper**. Refer this [KB document](https://www.syncfusion.com/kb/5390/how-to-parse-the-recurrencerule-in-server-side).

## Reminder

Reminder option notifies all the appointments before some specific time. By default, it notifies before 5 minutes. Each and every appointment triggers the `Reminder` event and can utilize this event for other user actions like mailing particular event to someone or to do any kind of manipulations with the reminder appointments and so on.

**Enable**

To enable the reminder settings of the Schedule control, set the **Enable** property as `true` within the `ReminderSettings` option.

**Alert Before**

The ReminderSettings option includes another optional property **AlertBefore** that accepts integer value to denote the time before how long the reminder should be notified to the user.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" TimeZone="UTC 00:00" Reminder="reminderCustom" CurrentDate="5/2/2014">
    <ReminderSettings Enable="true" AlertBefore="10" />
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function reminderCustom(args) {
            alert("Reminder Appointment");
        }
    </script>
</asp:Content>

{% endhighlight %}

N> Whenever the reminder setting is enabled in the Scheduler with some specific value (in minutes) assigned to the **AlertBefore** property, the **Reminder** event gets triggered before this specified value. It includes the reminder appointment’s entire information in its arguments.

