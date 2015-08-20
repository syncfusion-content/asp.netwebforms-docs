---
layout: post
title: Customization
description: customization
platform: aspnet
control: Schedule
documentation: ug
---

# Customization

## Customized Appointment window 

* You can display your own customized appointment window instead of the default appointment window while double-clicking on the cells. To achieve this, you can use the event appointmentWindowOpen. 
* The customized window is designed with the dialog control separately.

This example explains you on how to add the customized appointment window using the following code example.


{% highlight html %}




<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Custom Window</span>

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" AppointmentWindowOpen="onAppointmentWindowOpen">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>

</div>



<div id="customWindow" style="display: none">

<div>

<div id="custom">

<table width="100%" cellpadding="5">

<tbody>

<tr style="display: none">

<td>Id:

</td>

<td colspan="2">

<input id="customId" type="text" name="Id" />

</td>

</tr>

<tr>

<td>Subject:

</td>

<td colspan="2">

<input id="subject" type="text" value="" name="Subject" onfocus="temp()" style="width: 100%" />

</td>

</tr>

<tr>

<td>Description:

</td>

<td colspan="2">

<textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>

</td>

</tr>

<tr>

<td>StartTime:

</td>

<td>

<ej:DateTimePicker runat="server" ID="StartTime" Width="150"></ej:DateTimePicker>

</td>

</tr>

<tr>

<td>EndTime:

</td>

<td>

<ej:DateTimePicker runat="server" ID="EndTime" Width="150"></ej:DateTimePicker>

</td>

</tr>

<tr>

<td colspan="3">

<div class="customcheck">AllDay:</div>

<div class="customcheck">

<input id="allday" type="checkbox" name="AllDay" />

</div>

<div class="customcheck">Recurrence:</div>

<div>

<input id="recurrence" type="checkbox" name="Recurrence" onchange="recurCheck()" />

</div>

</td>

</tr>

<tr class="recurrence" style="display: none">

<td>Type:

</td>

<td>

<select id="rType" name="freq">

<option value="daily">Daily</option>

<option value="weekly">Weekly</option>

<option value="monthly">Monthly</option>

<option value="yearly">Yearly</option>

</select>

</td>

</tr>

</tbody>

</table>

</div>

<div>

<button type="submit" onclick="save()">

Submit</button>

<button type="submit" onclick="cancel()">

Cancel</button>

</div>

</div>

</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

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

</script>

</asp:Content>

<asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection">

<style type="text/css">

.customcheck {

float: left;

margin-right: 10px;

}



.error {

background-color: #FF8A8A;

}

</style>

</asp:Content>

{% endhighlight %}

Execute the above code and then double-click on the required Schedule cells. The customized appointment window is opened instead of the default appointment window as follows.



![](Customization_images/Customization_img1.png)


* Add the required details on the above displayed appointment window and then click Submit button to save the appointment.



## Editing Customized Appointment window

* To edit the appointments in customized appointment window, you can use appointmentWindowOpen event to avoid displaying the default appointment window when you double-click the appointments. 
* The customized window is designed with the dialog control separately and it is display when you double-click appointments. 

The following code example is added to the previous code example of appointment creation for Customized Appointment window.


{% highlight html %}

<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Custom Window</span>

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

<ej:Schedule ClientIDMode="Static"  runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" AppointmentWindowOpen="onAppointmentWindowOpen">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>

</div>



<div id="customWindow" style="display: none">

<div>

<div id="custom">

<table width="100%" cellpadding="5">

<tbody>

<tr style="display: none">

<td>Id:

</td>

<td colspan="2">

<input id="customId" type="text" name="Id" />

</td>

</tr>

<tr>

<td>Subject:

</td>

<td colspan="2">

<input id="subject" type="text" value="" name="Subject" onfocus="temp()" style="width: 100%" />

</td>

</tr>

<tr>

<td>Description:

</td>

<td colspan="2">

<textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>

</td>

</tr>

<tr>

<td>StartTime:

</td>

<td>

<ej:DateTimePicker runat="server" ID="StartTime" Width="150"></ej:DateTimePicker>

</td>

</tr>

<tr>

<td>EndTime:

</td>

<td>

<ej:DateTimePicker runat="server" ID="EndTime" Width="150"></ej:DateTimePicker>

</td>

</tr>

<tr>

<td colspan="3">

<div class="customcheck">AllDay:</div>

<div class="customcheck">

<input id="allday" type="checkbox" name="AllDay" />

</div>

<div class="customcheck">Recurrence:</div>

<div>

<input id="recurrence" type="checkbox" name="Recurrence" onchange="recurCheck()" />

</div>

</td>

</tr>

<tr class="recurrence" style="display: none">

<td>Type:

</td>

<td>

<select id="rType" name="freq">

<option value="daily">Daily</option>

<option value="weekly">Weekly</option>

<option value="monthly">Monthly</option>

<option value="yearly">Yearly</option>

</select>

</td>

</tr>

</tbody>

</table>

</div>

<div>

<button type="submit" onclick="save()">

Submit</button>

<button type="submit" onclick="cancel()">

Cancel</button>

</div>

</div>

</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

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

</script>

</asp:Content>

<asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection">

<style type="text/css">

.customcheck {

float: left;

margin-right: 10px;

}



.error {

background-color: #FF8A8A;

}

</style>

</asp:Content>


{% endhighlight %}


* Only the bolded texts in the above code examples are added to open the custom appointment window when you double-click the appointments. Execute the above code and then double-click on the appointment, the custom appointment window is displayed as follows.



![](Customization_images/Customization_img2.png)


_Figure_ _68_: schedule with appointment using customized appointment window._

* You can change the details in the above window and then click Submit button to save the updated values.



## Hour Customization

###Schedule Start/End Hour

You can customize the appearance of the Schedule control by setting the specific start and end hour to it. To set the specific start/end hour for a Schedule control, the following properties are required to be used.

###startHour

* Specify the start hour to set for the Schedule control.

###endHour

* Specify the end hour to set for the Schedule control.


{% highlight html %}



// setting the schedule start and end hour


<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="500px"

StartHour="4"

EndHour="24">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

Execute the above code to render the output as follows with the Schedule control beginning with 08.00am and ending with 06.00pm.



![](Customization_images/Customization_img3.png)


Figure 107 :  schedule with hour customization.

### Business hours

* There is an option highlightBusinessHours in the Schedule control to enable/disable the action of highlighting the business hours. 
* It is controlled with two additional options businessStartHour and businessEndHour to specify the time range to be defined as the business hours. By default, the business hours are highlighted in the Schedule control.

#### businessStartHour

* It allows you to specify the start time to indicate the business start hour.

#### businessEndHour

* It allows you to specify the end time to indicate the business end hour.





* To enable the highlightBusinessHours and to customize the business start and end hours, refer the following code example.


{% highlight html %}




<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" BusinessEndHour="18"

BusinessStartHour="10"

HighlightBusinessHours="True"

Height="800px" ShowCurrentTimeIndicator="True"

ShowQuickWindow="True"

Width="100%">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>


{% endhighlight %}
Execute the above code to render the following output that explains the highlighting of business hours in the Schedule control from 10.00am to 3.00pm.

![](Customization_images/Customization_img4.png)

   Figure 108 :  schedule with Business hours





## Date/Time Customization

### Current date

* By default, the Schedule control displays the current system date. 
* You can change the current date of the Schedule control by setting the currentDate option with the required date value. 

The following code example explains how to change the current date of the Schedule control.


{% highlight html %}



<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="525px"

CurrentDate="5/4/2014">



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

Execute the above code and the following screenshot displays the Schedule control with the current date set to (May 05, 2014).



![](Customization_images/Customization_img5.png)


  Figure 118:  schedule with current time

###Date Format

* The Schedule control uses different types of date formats to denote the dates used in it. You can specify your required format for the dates by using the dateFormat property. 
* When the date format is explicitly defined with particular value such as “dd-MM-yyyy”, then the datepicker control that is used within the Schedule control make use of this specific format.

The following code example explains how to change the dateFormat of the Schedule control.  


{% highlight html %}




<%-- Setting the DateFormat to the schedule -- %>





<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" DateFormat="dd-MM-yyyy">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

The following screenshot displays the Schedule control with the dateFormat set as “dd-MM-yyyy”.



![C:/Users/karthigeyan/Desktop/a.png](Customization_images/Customization_img6.png)


###Minimum and Maximum Dates

* This feature allows you to specify the minimum and maximum dates for the Schedule control. It can be defined with the minDate and maxDate properties. 
* Specifying minimum and maximum dates is especially useful when scheduling appointments for a project with fixed start and end dates.
* When these minimum and maximum dates are set, the dates apart from the specified range act as invalid/disabled dates and navigation beyond those dates are not possible.

The following code example explains how to set the minimum and maximum date of the Schedule control.  











{% highlight html %}





<%-- Sets the minimum and maximum date to the schedule -- %>

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/12/2014" MinDate="5/5/2014" MaxDate="5/25/2014" >

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

The following screenshot displays the Schedule control with MinDate and MaxDate set to 11/25/2014 and 12/4/2014, respectively.

![](Customization_images/Customization_img7.png)




###Timemode

* You can set two types of time mode, either 12 or 24 hour format for the Schedule control.  It accepts the following enum values,
1. ej.Schedule.TimeMode.Hour12
2. ej.Schedule.TimeMode.Hour24
* Set the Schedule control to 24 hour time mode using the following code example.




{% highlight html %}


// setting the 24 hour mode for the schedule


<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px"

TimeMode="Hour24">



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

The following screenshot displays the Schedule control when time mode is set to 24 hour mode.



![](Customization_images/Customization_img8.png)


   Figure 114 :  schedule time customization.

###TimeZone

* Appointments within the Schedule control is displayed based on the provided timezone. 
* If no specific timezones are set for the Schedule control, then it takes the local system timezone into consideration.
* [Click here](http://en.wikipedia.org/wiki/List_of_tz_database_time_zones) to see the complete list of supported timezones.

You can set the timezone to the Schedule control as follows. 









{% highlight html %}





<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Template</span>

</asp:Content>



<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" AppointmentTemplateId="#MyTemplate" TimeZone="UTC +3:00"  CurrentDate="5/2/2014">

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [Template]"></asp:SqlDataSource>

</asp:Content>

<asp:Content ID="styleContent" runat="server" ContentPlaceHolderID="StyleSection">

<style type="text/css">

.e-monthappointment

{

height:auto !important;

}

img

{

height:30px;

width:30px;

}

</style>

</asp:Content>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">

<script id="MyTemplate" type="text/x-jsrender">

<div style="height: 100%">

<div style="float: left; width: 24px;">

{{:~format(StartTime)}}

</div>

<div>

<div>{{:"UTC +3:00"}}</div>

</div>

</div>

</script>

<script type="text/javascript">

function _getImages(date) {

switch (new Date(date).getDay()) {

case 0:

return "<img src='../Content/images/Schedule/cake.png' />"

break;

case 1:

return "<img src='../Content/images/Schedule/basketball.png'/>"

break;

case 2:

return "<img src='../Content/images/Schedule/rugby.png'/>"

break;

case 3:

return "<img src='../Content/images/Schedule/guitar.png'/>"

break;

case 4:

return "<img src='../Content/images/Schedule/music.png'/>"

break;

case 5:

return "<img src='../Content/images/Schedule/doctor.png'/>"

break;

case 6:

return "<img src='../Content/images/Schedule/beach.png'/>"

break;

}

}

$.views.helpers({ format: _getImages });

</script>

</asp:Content>

{% endhighlight %}

* Add new appointments to the Schedule control. The appointments are rendered based on the time difference that tends to the timezone set to it.



















![](Customization_images/Customization_img9.png)


  Figure 115 :  schedule with timezone.

* In the above output, an appointment is initially created in the time-range 7.00am - 8.30am, it is saved in the timeslot between 9.00am – 10.30 am due to the time zone set to “UTC +2:00” in the Schedule control.





##Current Time indicator

* The current time indicator denotes the current system time and it is marked on the Schedule control with a horizontal line drawn across the current date. 
* The showCurrentTimeIndicator property allows you to show/hide the time indicator on the Schedule control.

The following screenshot displays the Schedule control with the current time indicator marked with 5.41 AM across the date 30 April, 2014,



![](Customization_images/Customization_img10.png)


 Figure 116 :  schedule time customization

The following code example explains how to disable the current time indicator from the Schedule control. 


{% highlight html %}



<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData"

Width="100%" Height="525px"

ShowCurrentTimeIndicator="false">



<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>



<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

* After setting showCurrentTimeIndicator property to ‘false’, the Schedule control is displayed without the current time indicator as follows.



![](Customization_images/Customization_img11.png)


Figure 117 :  schedule with show current time indicator.


## Show/Hide TimeScale

The TimeScale depicting the time duration (either in 12 or 24 hour format) is usually displayed at the left side of the schedule control. It can be shown or hidden from the Schedule control by using the showTimeScale property that is supported in both the Schedule orientations (Vertical and Horizontal). It is set to true, by default. The following code example explains on how to use the showTimeScale property.


{% highlight html %}


<%-- Show / Hide TimeScale property to the schedule -- %>
 
<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">
<div>
<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/12/2014" ShowTimeScale ="false">
 
<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>
</ej:Schedule>
 
</div>
<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"
SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

![](Customization_images/Customization_img12.png)

Figure 80: Schedule without TimeScale