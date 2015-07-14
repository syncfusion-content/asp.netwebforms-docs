---
layout: post
title: Customization
description: customization
platform: aspnet
control: Schedule
documentation: ug
---

## Customization

### Customized Appointment window 

* You can display your own customized appointment window instead of the default appointment window while double-clicking on the cells. To achieve this, you can use the event appointmentWindowOpen. 
* The customized window is designed with the dialog control separately.

This example explains you on how to add the customized appointment window using the following code example.



[ASP]



&lt;asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server"&gt;

<span class="sampleName">Schedule / Custom Window</span>

&lt;/asp:Content&gt;

&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div&gt;

&lt;ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" AppointmentWindowOpen="onAppointmentWindowOpen"&gt;

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;

&lt;/div&gt;



&lt;div id="customWindow" style="display: none"&gt;

&lt;div&gt;

&lt;div id="custom"&gt;

&lt;table width="100%" cellpadding="5"&gt;

&lt;tbody&gt;

&lt;tr style="display: none"&gt;

<td>Id:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;input id="customId" type="text" name="Id" /&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>Subject:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;input id="subject" type="text" value="" name="Subject" onfocus="temp()" style="width: 100%" /&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>Description:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"&gt;&lt;/textarea&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>StartTime:

&lt;/td&gt;

&lt;td&gt;

&lt;ej:DateTimePicker runat="server" ID="StartTime" Width="150"&gt;&lt;/ej:DateTimePicker&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>EndTime:

&lt;/td&gt;

&lt;td&gt;

&lt;ej:DateTimePicker runat="server" ID="EndTime" Width="150"&gt;&lt;/ej:DateTimePicker&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

&lt;td colspan="3"&gt;

<div class="customcheck">AllDay:&lt;/div&gt;

&lt;div class="customcheck"&gt;

&lt;input id="allday" type="checkbox" name="AllDay" /&gt;

&lt;/div&gt;

<div class="customcheck">Recurrence:&lt;/div&gt;

&lt;div&gt;

&lt;input id="recurrence" type="checkbox" name="Recurrence" onchange="recurCheck()" /&gt;

&lt;/div&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr class="recurrence" style="display: none"&gt;

<td>Type:

&lt;/td&gt;

&lt;td&gt;

&lt;select id="rType" name="freq"&gt;

<option value="daily">Daily</option>

<option value="weekly">Weekly</option>

<option value="monthly">Monthly</option>

<option value="yearly">Yearly</option>

&lt;/select&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;/tbody&gt;

&lt;/table&gt;

&lt;/div&gt;

&lt;div&gt;

&lt;button type="submit" onclick="save()"&gt;

Submit</button>

&lt;button type="submit" onclick="cancel()"&gt;

Cancel</button>

&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

&lt;script type="text/javascript"&gt;

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



});



function onAppointmentWindowOpen(args) {

args.cancel = true;

var quickobj = $("#Schedule1AppointmentQuickWindow").data("ejDialog");

quickobj.close();

$("#StartTime").ejDateTimePicker({ value: args.startTime });

$("#EndTime").ejDateTimePicker({ value: args.endTime });

if (!ej.isNullOrUndefined(args.target)) {

if ($(args.target.currentTarget).hasClass("e-alldaycells"))

$("#allday").prop("checked", true);

}

if (!ej.isNullOrUndefined(args.appointment)) {

if (args.appointment.Recurrence)

$("#customId").val(args.appointment.ParentId);

else

$("#customId").val(args.appointment.Id);

$("#subject").val(args.appointment.Subject);

$("#customdescription").val(args.appointment.Description);

$("#StartTime").ejDateTimePicker({ value: new Date(args.appointment.StartTime) });

$("#EndTime").ejDateTimePicker({ value: new Date(args.appointment.EndTime) });

$("#allday").prop("checked", args.appointment.AllDay);

$("#recurrence").prop("checked", args.appointment.Recurrence);

if (args.appointment.Recurrence) {

$("#rType").val(args.appointment.RecurrenceRule.split(";")[0].split("=")[1].toLowerCase());

$("tr.recurrence").css("display", "table-row");

}

$("#customWindow").ejDialog("open");

}

else

$("#customWindow").ejDialog("open");

}



function save() {

if ($("#subject").val().trim() == "") {

$("#subject").addClass("error");

return false;

}

var obj = {},temp = {}, rType;

obj["Id"] = $("#customId").val() == "" ? $("#customId").val() : parseInt($("#customId").val());

obj["Subject"] = $("#subject")[0].value;

obj["Description"] = $("#customdescription")[0].value;

obj["StartTime"] = new Date($("#StartTime")[0].value);

obj["EndTime"] = new Date($("#EndTime")[0].value);

obj["AllDay"] = $("#allday")[0].checked;

obj["Recurrence"] = $("#recurrence")[0].checked;

if ($("#recurrence")[0].checked) {

if ($("#rType")[0].value.toUpperCase() == "DAILY")

obj["RecurrenceRule"] = "FREQ=DAILY;INTERVAL=1;COUNT=5";

else if ($("#rType")[0].value.toUpperCase() == "WEEKLY")

obj["RecurrenceRule"] = "FREQ=WEEKLY;BYDAY=MO,WE,TH;INTERVAL=1;COUNT=10";

else if ($("#rType")[0].value.toUpperCase() == "MONTHLY")

obj["RecurrenceRule"] = "FREQ=MONTHLY;BYMONTHDAY=" + obj.StartTime.getDate() + ";INTERVAL=1;COUNT=5";

else if ($("#rType")[0].value.toUpperCase() == "YEARLY")

obj["RecurrenceRule"] = "FREQ=YEARLY;BYMONTHDAY=" + obj.StartTime.getDate() + ";BYMONTH=" + (obj.StartTime.getMonth() + 1) + ";INTERVAL=1;COUNT=3";

}

else

obj["RecurrenceRule"] = null;

$("#customWindow").ejDialog("close");

var object = $("#Schedule1").data("ejSchedule");

object.saveAppointment(obj);

clearFields();

}



function clearFields() {

$("#customId").val("");

$("#subject").val("");

$("#customdescription").val("");

$("#allday").prop("checked", false);

$("#recurrence").prop("checked", false);

document.getElementById("rType").selectedIndex = "0";

$("tr.recurrence").css("display", "none");

}



function recurCheck() {

if ($("#recurrence").get(0).checked == true)

$("tr.recurrence").css("display", "table-row");

else

$("tr.recurrence").css("display", "none");

}



function temp() {

$("#subject").removeClass("error");

}



function cancel() {

clearFields();

$("#customWindow").ejDialog("close");

}

&lt;/script&gt;

&lt;/asp:Content&gt;

&lt;asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection"&gt;

&lt;style type="text/css"&gt;

.customcheck {

float: left;

margin-right: 10px;

}



.error {

background-color: #FF8A8A;

}

&lt;/style&gt;

&lt;/asp:Content&gt;



Execute the above code and then double-click on the required Schedule cells. The customized appointment window is opened instead of the default appointment window as follows.



{ ![](Customization_images/Customization_img1.png) | markdownify }
{:.image }


* Add the required details on the above displayed appointment window and then click Submit button to save the appointment.



### Editing Customized Appointment window

* To edit the appointments in customized appointment window, you can use appointmentWindowOpen event to avoid displaying the default appointment window when you double-click the appointments. 
* The customized window is designed with the dialog control separately and it is display when you double-click appointments. 

The following code example is added to the previous code example of appointment creation for Customized Appointment window.



[ASP]

&lt;asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server"&gt;

<span class="sampleName">Schedule / Custom Window</span>

&lt;/asp:Content&gt;

&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div&gt;

&lt;ej:Schedule ClientIDMode="Static"  runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" AppointmentWindowOpen="onAppointmentWindowOpen"&gt;

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;

&lt;/div&gt;



&lt;div id="customWindow" style="display: none"&gt;

&lt;div&gt;

&lt;div id="custom"&gt;

&lt;table width="100%" cellpadding="5"&gt;

&lt;tbody&gt;

&lt;tr style="display: none"&gt;

<td>Id:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;input id="customId" type="text" name="Id" /&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>Subject:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;input id="subject" type="text" value="" name="Subject" onfocus="temp()" style="width: 100%" /&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>Description:

&lt;/td&gt;

&lt;td colspan="2"&gt;

&lt;textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"&gt;&lt;/textarea&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>StartTime:

&lt;/td&gt;

&lt;td&gt;

&lt;ej:DateTimePicker runat="server" ID="StartTime" Width="150"&gt;&lt;/ej:DateTimePicker&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

<td>EndTime:

&lt;/td&gt;

&lt;td&gt;

&lt;ej:DateTimePicker runat="server" ID="EndTime" Width="150"&gt;&lt;/ej:DateTimePicker&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr&gt;

&lt;td colspan="3"&gt;

<div class="customcheck">AllDay:&lt;/div&gt;

&lt;div class="customcheck"&gt;

&lt;input id="allday" type="checkbox" name="AllDay" /&gt;

&lt;/div&gt;

<div class="customcheck">Recurrence:&lt;/div&gt;

&lt;div&gt;

&lt;input id="recurrence" type="checkbox" name="Recurrence" onchange="recurCheck()" /&gt;

&lt;/div&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;tr class="recurrence" style="display: none"&gt;

<td>Type:

&lt;/td&gt;

&lt;td&gt;

&lt;select id="rType" name="freq"&gt;

<option value="daily">Daily</option>

<option value="weekly">Weekly</option>

<option value="monthly">Monthly</option>

<option value="yearly">Yearly</option>

&lt;/select&gt;

&lt;/td&gt;

&lt;/tr&gt;

&lt;/tbody&gt;

&lt;/table&gt;

&lt;/div&gt;

&lt;div&gt;

&lt;button type="submit" onclick="save()"&gt;

Submit</button>

&lt;button type="submit" onclick="cancel()"&gt;

Cancel</button>

&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

&lt;script type="text/javascript"&gt;

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



});



function onAppointmentWindowOpen(args) {

args.cancel = true;

var quickobj = $("#Schedule1AppointmentQuickWindow").data("ejDialog");

quickobj.close();

$("#StartTime").ejDateTimePicker({ value: args.startTime });

$("#EndTime").ejDateTimePicker({ value: args.endTime });

if (!ej.isNullOrUndefined(args.target)) {

if ($(args.target.currentTarget).hasClass("e-alldaycells"))

$("#allday").prop("checked", true);

}

if (!ej.isNullOrUndefined(args.appointment)) {

if (args.appointment.Recurrence)

$("#customId").val(args.appointment.ParentId);

else

$("#customId").val(args.appointment.Id);

$("#subject").val(args.appointment.Subject);

$("#customdescription").val(args.appointment.Description);

$("#StartTime").ejDateTimePicker({ value: new Date(args.appointment.StartTime) });

$("#EndTime").ejDateTimePicker({ value: new Date(args.appointment.EndTime) });

$("#allday").prop("checked", args.appointment.AllDay);

$("#recurrence").prop("checked", args.appointment.Recurrence);

if (args.appointment.Recurrence) {

$("#rType").val(args.appointment.RecurrenceRule.split(";")[0].split("=")[1].toLowerCase());

$("tr.recurrence").css("display", "table-row");

}

$("#customWindow").ejDialog("open");

}

else

$("#customWindow").ejDialog("open");

}



function save() {

if ($("#subject").val().trim() == "") {

$("#subject").addClass("error");

return false;

}

var obj = {},temp = {}, rType;

obj["Id"] = $("#customId").val() == "" ? $("#customId").val() : parseInt($("#customId").val());

obj["Subject"] = $("#subject")[0].value;

obj["Description"] = $("#customdescription")[0].value;

obj["StartTime"] = new Date($("#StartTime")[0].value);

obj["EndTime"] = new Date($("#EndTime")[0].value);

obj["AllDay"] = $("#allday")[0].checked;

obj["Recurrence"] = $("#recurrence")[0].checked;

if ($("#recurrence")[0].checked) {

if ($("#rType")[0].value.toUpperCase() == "DAILY")

obj["RecurrenceRule"] = "FREQ=DAILY;INTERVAL=1;COUNT=5";

else if ($("#rType")[0].value.toUpperCase() == "WEEKLY")

obj["RecurrenceRule"] = "FREQ=WEEKLY;BYDAY=MO,WE,TH;INTERVAL=1;COUNT=10";

else if ($("#rType")[0].value.toUpperCase() == "MONTHLY")

obj["RecurrenceRule"] = "FREQ=MONTHLY;BYMONTHDAY=" + obj.StartTime.getDate() + ";INTERVAL=1;COUNT=5";

else if ($("#rType")[0].value.toUpperCase() == "YEARLY")

obj["RecurrenceRule"] = "FREQ=YEARLY;BYMONTHDAY=" + obj.StartTime.getDate() + ";BYMONTH=" + (obj.StartTime.getMonth() + 1) + ";INTERVAL=1;COUNT=3";

}

else

obj["RecurrenceRule"] = null;

$("#customWindow").ejDialog("close");

var object = $("#Schedule1").data("ejSchedule");

object.saveAppointment(obj);

clearFields();

}



function clearFields() {

$("#customId").val("");

$("#subject").val("");

$("#customdescription").val("");

$("#allday").prop("checked", false);

$("#recurrence").prop("checked", false);

document.getElementById("rType").selectedIndex = "0";

$("tr.recurrence").css("display", "none");

}



function recurCheck() {

if ($("#recurrence").get(0).checked == true)

$("tr.recurrence").css("display", "table-row");

else

$("tr.recurrence").css("display", "none");

}



function temp() {

$("#subject").removeClass("error");

}



function cancel() {

clearFields();

$("#customWindow").ejDialog("close");

}

&lt;/script&gt;

&lt;/asp:Content&gt;

&lt;asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection"&gt;

&lt;style type="text/css"&gt;

.customcheck {

float: left;

margin-right: 10px;

}



.error {

background-color: #FF8A8A;

}

&lt;/style&gt;

&lt;/asp:Content&gt;





* Only the bolded texts in the above code examples are added to open the custom appointment window when you double-click the appointments. Execute the above code and then double-click on the appointment, the custom appointment window is displayed as follows.



{ ![](Customization_images/Customization_img2.png) | markdownify }
{:.image }


_Figure_ _68__: schedule with appointment using customized appointment window._

* You can change the details in the above window and then click Submit button to save the updated values.



### Hour Customization

Schedule Start/End Hour

You can customize the appearance of the Schedule control by setting the specific start and end hour to it. To set the specific start/end hour for a Schedule control, the following properties are required to be used.

startHour

* Specify the start hour to set for the Schedule control.

endHour

* Specify the end hour to set for the Schedule control.



[ASP]



// setting the schedule start and end hour

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="500px"

StartHour="4"

EndHour="24">

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



Execute the above code to render the output as follows with the Schedule control beginning with 08.00am and ending with 06.00pm.



{ ![](Customization_images/Customization_img3.png) | markdownify }
{:.image }


_Figure_ _107__:  schedule with hour customization._

Business hours

* There is an option highlightBusinessHours in the Schedule control to enable/disable the action of highlighting the business hours. 
* It is controlled with two additional options businessStartHour and businessEndHour to specify the time range to be defined as the business hours. By default, the business hours are highlighted in the Schedule control.

businessStartHour

* It allows you to specify the start time to indicate the business start hour.

businessEndHour

* It allows you to specify the end time to indicate the business end hour.





* To enable the highlightBusinessHours and to customize the business start and end hours, refer the following code example.



[ASP]



<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" BusinessEndHour="18"

BusinessStartHour="10"

HighlightBusinessHours="True"

Height="800px" ShowCurrentTimeIndicator="True"

ShowQuickWindow="True"

Width="100%">

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



Execute the above code to render the following output that explains the highlighting of business hours in the Schedule control from 10.00am to 3.00pm.

{ ![](Customization_images/Customization_img4.png) | markdownify }
{:.image }


   _Figure_ _108__:  schedule with Business hours_





### Date/Time Customization

Current date

* By default, the Schedule control displays the current system date. 
* You can change the current date of the Schedule control by setting the currentDate option with the required date value. 

The following code example explains how to change the current date of the Schedule control.



[ASP]

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="525px"

CurrentDate="5/4/2014">



&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



Execute the above code and the following screenshot displays the Schedule control with the current date set to (May 05, 2014).



{ ![](Customization_images/Customization_img5.png) | markdownify }
{:.image }


  _Figure_ _118__:  schedule with current time_

Date Format

* The Schedule control uses different types of date formats to denote the dates used in it. You can specify your required format for the dates by using the dateFormat property. 
* When the date format is explicitly defined with particular value such as “dd-MM-yyyy”, then the datepicker control that is used within the Schedule control make use of this specific format.

The following code example explains how to change the dateFormat of the Schedule control.  



[ASP]



&lt;%-- Setting the DateFormat to the schedule -- %&gt;





&lt;ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" DateFormat="dd-MM-yyyy"&gt;

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



The following screenshot displays the Schedule control with the dateFormat set as “dd-MM-yyyy”.



{ ![C:/Users/karthigeyan/Desktop/a.png](Customization_images/Customization_img6.png) | markdownify }
{:.image }


Minimum and Maximum Dates

* This feature allows you to specify the minimum and maximum dates for the Schedule control. It can be defined with the minDate and maxDate properties. 
* Specifying minimum and maximum dates is especially useful when scheduling appointments for a project with fixed start and end dates.
* When these minimum and maximum dates are set, the dates apart from the specified range act as invalid/disabled dates and navigation beyond those dates are not possible.

The following code example explains how to set the minimum and maximum date of the Schedule control.  













[ASP]



&lt;%-- Sets the minimum and maximum date to the schedule -- %&gt;

&lt;ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/12/2014" MinDate="5/5/2014" MaxDate="5/25/2014" &gt;

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



The following screenshot displays the Schedule control with MinDate and MaxDate set to 11/25/2014 and 12/4/2014, respectively.

{ ![](Customization_images/Customization_img7.png) | markdownify }
{:.image }




Timemode

* You can set two types of time mode, either 12 or 24 hour format for the Schedule control.  It accepts the following enum values,
1. ej.Schedule.TimeMode.Hour12
2. ej.Schedule.TimeMode.Hour24
* Set the Schedule control to 24 hour time mode using the following code example.





[ASP]

// setting the 24 hour mode for the schedule

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px"

TimeMode="Hour24">



&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



The following screenshot displays the Schedule control when time mode is set to 24 hour mode.



{ ![](Customization_images/Customization_img8.png) | markdownify }
{:.image }


   _Figure_ _114__:  schedule time customization._

TimeZone

* Appointments within the Schedule control is displayed based on the provided timezone. 
* If no specific timezones are set for the Schedule control, then it takes the local system timezone into consideration.
* [Click here](http://en.wikipedia.org/wiki/List_of_tz_database_time_zones) to see the complete list of supported timezones.

You can set the timezone to the Schedule control as follows. 











[ASP]



&lt;asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server"&gt;

<span class="sampleName">Schedule / Template</span>

&lt;/asp:Content&gt;



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div&gt;

&lt;ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" AppointmentTemplateId="#MyTemplate" TimeZone="UTC +3:00"  CurrentDate="5/2/2014"&gt;

&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [Template]">&lt;/asp:SqlDataSource&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="styleContent" runat="server" ContentPlaceHolderID="StyleSection"&gt;

&lt;style type="text/css"&gt;

.e-monthappointment

{

height:auto !important;

}

img

{

height:30px;

width:30px;

}

&lt;/style&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

&lt;script id="MyTemplate" type="text/x-jsrender"&gt;

&lt;div style="height: 100%"&gt;

&lt;div style="float: left; width: 24px;"&gt;

{{:~format(StartTime)}}

&lt;/div&gt;

&lt;div&gt;

&lt;div&gt;{{:"UTC +3:00"}}&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/script&gt;

&lt;script type="text/javascript"&gt;

function _getImages(date) {

switch (new Date(date).getDay()) {

case 0:

return "&lt;img src='../Content/images/Schedule/cake.png' /&gt;"

break;

case 1:

return "&lt;img src='../Content/images/Schedule/basketball.png'/&gt;"

break;

case 2:

return "&lt;img src='../Content/images/Schedule/rugby.png'/&gt;"

break;

case 3:

return "&lt;img src='../Content/images/Schedule/guitar.png'/&gt;"

break;

case 4:

return "&lt;img src='../Content/images/Schedule/music.png'/&gt;"

break;

case 5:

return "&lt;img src='../Content/images/Schedule/doctor.png'/&gt;"

break;

case 6:

return "&lt;img src='../Content/images/Schedule/beach.png'/&gt;"

break;

}

}

$.views.helpers({ format: _getImages });

&lt;/script&gt;

&lt;/asp:Content&gt;



* Add new appointments to the Schedule control. The appointments are rendered based on the time difference that tends to the timezone set to it.



















{ ![](Customization_images/Customization_img9.png) | markdownify }
{:.image }


  _Figure_ _115__:  schedule with timezone._

* In the above output, an appointment is initially created in the time-range 7.00am - 8.30am, it is saved in the timeslot between 9.00am – 10.30 am due to the time zone set to “UTC +2:00” in the Schedule control.





Current Time indicator

* The current time indicator denotes the current system time and it is marked on the Schedule control with a horizontal line drawn across the current date. 
* The showCurrentTimeIndicator property allows you to show/hide the time indicator on the Schedule control.

The following screenshot displays the Schedule control with the current time indicator marked with 5.41 AM across the date 30 April, 2014,



{ ![](Customization_images/Customization_img10.png) | markdownify }
{:.image }


 _Figure_ _116__:  schedule time customization_

The following code example explains how to disable the current time indicator from the Schedule control. 



[ASP]

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="525px"

ShowCurrentTimeIndicator="false">



&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;

&lt;/ej:Schedule&gt;



&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [DefaultSchedule]">&lt;/asp:SqlDataSource&gt;



* After setting showCurrentTimeIndicator property to ‘false’, the Schedule control is displayed without the current time indicator as follows.



{ ![](Customization_images/Customization_img11.png) | markdownify }
{:.image }


_Figure_ _117__:  schedule with show current time indicator._



