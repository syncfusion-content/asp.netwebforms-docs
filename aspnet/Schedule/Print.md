---
layout: post
title: Print
description: print
platform: aspnet
control: Schedule
documentation: ug
---

# Print

Schedule control is provided with the Print feature. You can print the entire Schedule control or separately print the appointment based on your requirement.

## Schedule Print

You can print the Schedule control by using print() method. Use the following code example to print the Schedule control.


{% highlight html %}




<div>

<input class="print" type="button" value="Print" />

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData">

<%--Add the Necessary properties here -- %>

</ej:Schedule>

</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<script type="text/javascript">

$(document).ready(function () {



// function to bind the click event to the button



$('.print').bind("click", function () {



var obj = $("#Schedule1").data("ejSchedule");



// Public method to print the schedule



obj.print();



});



});

</script>

{% endhighlight %}

Execute the above code to render the following output.

![](Print_images/Print_img1.png)


Figure 121 : Schedule with print button

Click the print button to render the following output.



![](Print_images/Print_img2.png)


Figure 122 : Schedule with Print window

## Appointment Print

* In Schedule control, you can print the appointment alone by using context menu. Add print as menu item in the context menu settings as in the following code example. 

{% highlight html %}




<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData">

<%--To Add the Context menu setting-- %>

<ContextMenuSettings Enable="true">

<%--To Add the Context menu setting-- %>

<MenuItems>

<AppointmentCollection>

<ej:Appointment Id="open" Text="Open Appointment" />

<ej:Appointment Id="delete" Text="Delete Appointment" />

<%--To Add the print item in that collection-- %>

<ej:Appointment Id="print" Text="Print Appointment" />

</AppointmentCollection>

</MenuItems>

</ContextMenuSettings>

<%--Add the necessary schedule properties here-- %>

</ej:Schedule>

<div id="reminder">

<a class="pull-left" href="#" style="margin-top: 9px; outline: medium none;">

<div class="reminder-icon e-btn e-select /">

</a>

</div>

<style type="text/css">

#reminder

{

width: 50px;

height: 40px;

margin-top: 1px;

float: right;

}

.reminder-icon

{

background-image: url("../Content/images/Schedule/print.png") !important;

background-repeat:no-repeat !important;

background-position: 3px 3px !important;

border: 1px solid #BBBCBB !important;

height: 28px;

width: 28px;

}

</style>

<script type="text/javascript">

$(function () {

$("#Schedule1").find("tr.e-scheduleheader td").first().append($("#reminder"));

$('.reminder-icon').bind("click", function () {

var obj = $("#Schedule1").data("ejSchedule");

obj.print();

});

});



</script>

{% endhighlight %}

* Right click on the appointment and select print appointment in the context menu as follows.



![](Print_images/Print_img3.png)


Figure 123 : Schedule with Print option in Context Menu

* Now, the widow is promoted to new document with appointment details and print window opens.



![](Print_images/Print_img4.png)


Figure 124 : Schedule with Appointment Print

