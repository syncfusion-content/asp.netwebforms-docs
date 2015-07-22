---
layout: post
title: Reminder
description: reminder
platform: aspnet
control: Schedule
documentation: ug
---

# Reminder

* Reminder option provides the list of reminder appointments and you can use those appointments for your own customized scenarios like displaying it as an end-user notification. To enable the reminder settings for the Schedule control, you can set the enable property as ‘true’ within the reminderSettings option. 
* The reminderSettings option includes another optional property alertBefore that accepts integer value to denote the time before how long the reminder is notified to the user.
* For such case, you can also use an in-built event reminder that triggers when there is a reminder appointment. It provides the details of the list of reminder appointment details.

The following code example explains how to get the reminder list and display it as a notification for users.




{% highlight html %}




<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Reminder</span>

</asp:Content>



<asp:Content ID="Header" ContentPlaceHolderID="HeadSection" runat="server">

<script src='<%= Page.ResolveClientUrl("~/Scripts/bootstrap.min.js")%>' type="text/javascript"></script>

<script src='<%= Page.ResolveClientUrl("~/Scripts/bootstrap-notify.js")%>' type="text/javascript"></script>

<link href=".../Content/bootstrap-notify.css" rel="stylesheet" />

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<!-- Reminder list div elements-->

<div id="reminder" class="media" data-content=" ">

<a class="pull-left" href="#" style="margin-top: 9px; outline: medium none;">

<div class="reminder-icon">

</div>

<span id="reminderCount" class="badge badge-success pull-right">0</span> </a>

</div>

<!-- Notification div element-->

<div class='notifications bottom-right'>

</div>

<div>

<ej:Schedule runat="server" ID="Schedule1" Width="100%" Height="525px" Reminder="ongetReminderList" Create="onCreate">

<ReminderSettings Enable="true" AlertBefore="6"/>

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/>

</ej:Schedule>

</div>

</asp:Content>



<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">

<script type="text/javascript">

function onCreate() {

//Append the reminder list to the Schedule header

$("#Schedule1").find("tr.e-scheduleheader td").first().append($("#reminder"));

// Reminder list load to the popover control

$("#reminder").popover({ placement: 'bottom' });

//popover content has been updated

$('#reminder').on('shown.bs.popover', function () {

if (parseInt($("#reminderCount").text()) == 0)

return false;

$(".popover-content").html($_remList);

$(".outerDiv .close").on("click", function () {

$(this).parents(".outerDiv").remove();

$_remList = $(".popover-content").html();

$("#reminderCount").html(parseInt($("#reminderCount").text()) - 1);

checkList();

});

$(".outerDiv").on("mouseover", function () {

$(this).find(".close").show();

});

$(".outerDiv").on("mouseout", function () {

$(this).find(".close").hide();

});

});

}

function checkList() {

if (parseInt($("#reminderCount").text()) == 0)

$("#reminderCount").hide();

else

$("#reminderCount").show();

}

var $_remList = "";

function ongetReminderList(args) {

//alert(args.reminderAppointment.Subject);

$("#reminderCount").html(parseInt($("#reminderCount").text()) + 1);

checkList();

$_remList += "<div class='outerDiv'><span class='e-quicksubject'>" + args.reminderAppointment.Subject +

"</span><div class='e-quickstartendtime'>" + args.reminderAppointment.StartTime +

"</div><a class='close pull-right' href='#' style='margin-top: -56px;display: none;'>×</a></div>";

var notifiList = "<div><span class='e-quicksubject'>" + args.reminderAppointment.Subject +

"</span><div class='e-quickstartendtime'>" + args.reminderAppointment.StartTime +

"</div></div>";

// Show the notification div

$('.bottom-right').notify({

message: { html: notifiList },

type: "info",

fadeOut: {

enabled: false

}

}).show();

}

</script>

</asp:Content>

<asp:Content ID="styleSection" ContentPlaceHolderID="StyleSection" runat="server">

<style type="text/css">

#reminderCount

{

position: relative;

min-width: 6px;

top: -36px;

left: 10px;

background-color: #FF0000;

}

#reminder

{

width: 50px;

height: 40px;

margin-top: 3px;

float: right;

}

.reminder-icon

{

background: url("../Content/images/Schedule/bell.png") no-repeat scroll 8px 6px rgba(0, 0, 0, 0);

border: 1px solid #BBBCBB;

height: 28px;

width: 28px;

border-radius: 6px;

}

.popover.bottom .arrow

{

margin-top: 0px;

}

.popover

{

width: 300px;

}

.outerDiv

{

border-bottom: 1px solid #BBBCBB;

padding-bottom: 5px;

}

.notifications.top-right

{

top: 25% !important;

}

</style>

</asp:Content>

{% endhighlight %}

Execute the above code to render the following output.



![](Reminder_images/Reminder_img1.png)


   _Figure_ _106_:  schedule with Reminder._



