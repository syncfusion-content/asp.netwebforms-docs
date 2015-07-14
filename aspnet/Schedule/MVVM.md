---
layout: post
title: MVVM
description: mvvm
platform: aspnet
control: Schedule
documentation: ug
---

## MVVM

Angular JS

* Schedule contains angular support. You can add object as well as array object in the Schedule.
* The two way binding support is given to the currentView, currentDate and datasource properties. 
* ej-Schedule is the control tag in which ej is tag prefix and Schedule is the control name.

Rendering the Schedule

You can render the Schedule by using the following code example. Object in the array collection such as appointmentSetting, contextMenuSettings, etc. are extended with hyphen in the same tag.

Example: e-contextMenuSettings-enable.

&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div ng-app="syncApp"&gt;

&lt;div ng-controller="ScheduleCtrl"&gt;

<ej-Schedule style="float: left" id="Schedule1"

e-appointmentSettings-datasource="appointments"

e-appointmentSettings-id="Id"

e-appointmentSettings-subject="Subject"

e-appointmentSettings-startTime="StartTime"

e-appointmentSettings-endTime="EndTime"

e-appointmentSettings-description="Description"

e-appointmentSettings-allDay="AllDay"

e-appointmentSettings-recurrence="Recurrence"

e-appointmentSettings-recurrenceRule="RecurrenceRule"

e-width="100%" e-height="525px" e-currentview="setView"

e-currentdate="setDate" e-contextMenuSettings-enable="true">



&lt;/ej-Schedule&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/asp:Content&gt;

Adding Context menu settings

* Context menu is an object type that has inner array object. 
* contextMenuSettings contains an object called menuItem.
* Menu item has two types of array objects for cells and appointment respectively.

&lt;!--To Render the Schedule--&gt;



&lt;ej-Schedule style="float: left" id="Schedule1"&gt;



&lt;!--Adding content menu item for appointment --&gt;



&lt;e-contextMenuSettings-menuItems-appointment&gt;

&lt; e-appointment e-id="open" e-text="Open Appointment"&gt;&lt;/ e-appointment&gt;

&lt; e-appointment e-id="delete" e-text="Delete Appointment"&gt;&lt;/ e-appointment&gt;

&lt; e-appointment e-id="categorize" e-text="Delete Appointment"&gt;

&lt;/ e-appointment&gt;

&lt;/e-contextMenuSettings-menuItems-appointment&gt;



&lt;!--Adding content menu item for cells --&gt;

&lt;e-contextMenuSettings-menuItems-cells&gt;

<e-contextMenuSettings-menuItems-cell

e-id="new" e-text="Create New Appointment">

&lt;/e-contextMenuSettings-menuItems-cell&gt;



<e-contextMenuSettings-menuItems-cell

e-id="recurrence" e-text="Create recurrence Appointment">

&lt;/e-contextMenuSettings-menuItems-cell&gt;



&lt;/e-contextMenuSettings-menuItems-cells&gt;



&lt;/ej-Schedule&gt;

Adding Categorize option

* Categorizeoption is an array object. 
* contextMenuSettings contains an object called menuItem.
* Menu item has two types of array objects for cells and appointment respectively.

&lt;!--To Render the Schedule--&gt;



<ej-Schedule style="float: left" id="Schedule1" e-categorizesetting-enable="true"

e-categorizesetting-allowMultiple="true" e-categorizesetting-text="text"

e-categorizesetting-color="color"

e-categorizesetting-fontcolor="fontcolor" e-categorizesetting-id="id">



&lt;!--Adding content menu item for appointment --&gt;

&lt;e-contextMenuSettings-menuItems-appointment&gt;

&lt;/e-contextMenuSettings-menuItems-appointment&gt;



&lt;!--Adding content menu item for cells --&gt;



&lt;e-contextMenuSettings-menuItems-cells&gt;

&lt;/e-contextMenuSettings-menuItems-cells&gt;



&lt;e-categorizesetting-datasource&gt;



<e-categorizesetting-datasource text="Blue category"

color="Blue" fontcolor="Red" id="1">

&lt;/e-categorizesetting-datasource&gt;



<e-categorizesetting-datasource text="yellow category"

color="yellow" fontcolor="Red" id="2">

&lt;/e-categorizesetting-datasource&gt;



<e-categorizesetting-datasource text="red category" color="red"

fontcolor="Red" id="3">

&lt;/e-categorizesetting-datasource&gt;



<e-categorizesetting-datasource text="orange category" color="orange"

fontcolor="Red" id="4">

&lt;/e-categorizesetting-datasource&gt;



&lt;/e-categorizesetting-datasource&gt;



&lt;/ej-Schedule&gt;





Execute the above codes to render the Resultant schedule as follows.

{ ![](MVVM_images/MVVM_img1.png) | markdownify }
{:.image }


Two Way Binding 

* Schedule control supports two way binding for the property currentView , currentDate and datasource as mentioned earlier. 
* [Click here](http://asp.syncfusion.com/demos/web/schedule/angular.aspx) to see how Angular JS works with schedule.
* The following code example explains how to achieve the two way binding to the Schedule control.



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div ng-app="syncApp"&gt;

&lt;div ng-controller="ScheduleCtrl"&gt;

&lt;div&gt;

Current View

&lt;/div&gt;

&lt;input id="ddlView" ej-dropdownlist e-datasource="dataList" e-value="drpvalue" e-width="107px" /&gt;

&lt;div&gt;

Current Date

&lt;/div&gt;

&lt;input id="datepick1" ej-datepicker e-value="setDate" e-width="107px" /&gt;



<ej-Schedule style="float: left" width="400" id="Schedule1"

e-appointmentSettings-datasource="appointments"

e-appointmentSettings-id="Id" e-appointmentSettings-subject="Subject"

e-appointmentSettings-startTime="StartTime"

e-appointmentSettings-endTime="EndTime"

e-appointmentSettings-description="Description"

e-appointmentSettings-allDay="AllDay"

e-appointmentSettings-recurrence="Recurrence"

e-appointmentSettings-recurrenceRule="RecurrenceRule"

e-width="100%" e-height="525px" e-currentview="setView"

e-currentdate="setDate" e-contextMenuSettings-enable="true"

e-categorizesetting-enable="true" e-categorizesetting-allowMultiple="true"

e-categorizesetting-text="text" e-categorizesetting-color="color"

e-categorizesetting-fontcolor="fontcolor" e-categorizesetting-id="id">

&lt;e-categorizesetting-datasource&gt;

&lt;e-categorizesetting-datasource text="Blue category" color="Blue" fontcolor="Red" id="1"&gt;&lt;/e-categorizesetting-datasource&gt;

&lt;e-categorizesetting-datasource text="yellow category" color="yellow" fontcolor="Red" id="2"&gt;&lt;/e-categorizesetting-datasource&gt;

&lt;e-categorizesetting-datasource text="red category" color="red" fontcolor="Red" id="3"&gt;&lt;/e-categorizesetting-datasource&gt;

&lt;e-categorizesetting-datasource text="orange category" color="orange" fontcolor="Red" id="4"&gt;&lt;/e-categorizesetting-datasource&gt;

&lt;/e-categorizesetting-datasource&gt;

&lt;e-contextMenuSettings-menuItems-appointment&gt;             &lt;appointment e-id="open" e-text="Open Appointment"&gt;&lt;/appointment&gt;

&lt;appointment e-id="delete" e-text="Delete Appointment"&gt;&lt;/appointment&gt;

&lt;/e-contextMenuSettings-menuItems-appointment&gt;

&lt;e-contextMenuSettings-menuItems-cells&gt;

<e-contextMenuSettings-menuItems-cell

e-id="new" e-text="Create New Appointment">

&lt;/e-contextMenuSettings-menuItems-cell&gt;

<e-contextMenuSettings-menuItems-cell

e-id="recurrence" e-text="Create recurrence Appointment">

&lt;/e-contextMenuSettings-menuItems-cell&gt;

<e-contextMenuSettings-menuItems-cell

e-id="today" e-text="Today">

&lt;/e-contextMenuSettings-menuItems-cell&gt;

<e-contextMenuSettings-menuItems-cell

e-id="gotodate" -text="Go to date">

&lt;/e-contextMenuSettings-menuItems-cell&gt;

&lt;/e-contextMenuSettings-menuItems-cells&gt;

&lt;/ej-Schedule&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/asp:Content&gt;

&lt;script&gt;

&lt;!—binding the value to the scope variables in application controller--&gt;

var data = [

{ "Id": 1, "Subject": "Meeting", "StartTime": new Date(2014, 4, 1, 4), "EndTime": new Date(2014, 4, 1, 6), "AllDay": false, "Recurrence": false },

{ "Id": 2, "Subject": "Testing", "StartTime": new Date(2014, 4, 2, 4), "EndTime": new Date(2014, 4, 2, 6), "AllDay": false, "Recurrence": false },

{ "Id": 3, "Subject": "Review", "StartTime": new Date(2014, 4, 2, 2), "EndTime": new Date(2014, 4, 2, 3), "AllDay": false, "Recurrence": false },

{ "Id": 4, "Subject": "Conference", "StartTime": new Date(2014, 4, 3, 4), "EndTime": new Date(2014, 4, 3, 6), "AllDay": false, "Recurrence": false },

{ "Id": 5, "Subject": "Deployment", "StartTime": new Date(2014, 4, 3, 1), "EndTime": new Date(2014, 4, 3, 3), "AllDay": false, "Recurrence": false }



];

angular.module('syncApp', ['ejangular'])

.controller('ScheduleCtrl', function ($scope) {

$scope.appointments = data;

$scope.setView = "week";

$scope.setDate = new Date();

});

$("#sampleProperties").ejPropertiesPanel();

&lt;/script&gt;



Execute the above code to render the following output.

{ ![](MVVM_images/MVVM_img2.png) | markdownify }
{:.image }


Knockout binding

* Knockoutsupport allows you to bind the html elements against the available data models.Two types of knockoutbinding are supported,
1. one-way binding
2. two-way binding
* One way binding refers to the process of applying observable values to all the available properties of the Schedule control. The changes made in Schedule control is not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the Schedule control.
* Two-way binding supports both the processes – it applies the observable values to the Schedule properties along with the changes made in the Schedule control is reflected back and triggered within the observable collections. Only few Schedule properties support two-way binding and they are as follows.
1. currentView
2. currentDate
3. dataSource (within appointmentSettings object)
* Apply the plugin and property assigning to the Schedule element through the directive that starts with a letter “e-“. The following example depicts the way to bind data to the Schedule control through the knockoutsupport.
* [Click here](http://asp.syncfusion.com/demos/web/schedule/knockout.aspx) to see how Knockout binding works with schedule.





[ASP]

&lt;asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server"&gt;

<span class="sampleName">Schedule / Knockout Binding</span>

&lt;/asp:Content&gt;



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div&gt;

&lt;div style="float: left" id="Schedule1" data-bind="ejSchedule: { width: '100%', height: '525px', appointmentSettings: { dataSource: appointments, id: 'Id', subject: 'Subject', location: 'Location', description: 'Description', startTime: 'StartTime', endTime: 'EndTime', allDay: 'AllDay', recurrence: 'Recurrence', recurrenceRule: 'RecurrenceRule' }, currentView: view, currentDate: date }"&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"

SelectCommand="SELECT * FROM [Localization]">&lt;/asp:SqlDataSource&gt;

&lt;/asp:Content&gt;



&lt;asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

&lt;script type="text/javascript"&gt;

$(function () {

var data = [

{ "Id": 1, "Subject": "Meeting", "StartTime": new Date(2014, 4, 1, 4), "EndTime": new Date(2014, 4, 1, 6), "AllDay": false, "Recurrence": false },

{ "Id": 2, "Subject": "Testing", "StartTime": new Date(2014, 4, 2, 4), "EndTime": new Date(2014, 4, 2, 6), "AllDay": false, "Recurrence": false },

{ "Id": 3, "Subject": "Review", "StartTime": new Date(2014, 4, 2, 2), "EndTime": new Date(2014, 4, 2, 3), "AllDay": false, "Recurrence": false },

{ "Id": 4, "Subject": "Conference", "StartTime": new Date(2014, 4, 3, 4), "EndTime": new Date(2014, 4, 3, 6), "AllDay": false, "Recurrence": false },

{ "Id": 5, "Subject": "Deployment", "StartTime": new Date(2014, 4, 3, 1), "EndTime": new Date(2014, 4, 3, 3), "AllDay": false, "Recurrence": false }



];

window.viewModel = {

appointments: ko.observable(data),

view: ko.observable("week"),

date: ko.observable(new Date(2014, 4, 2))

};

$(function () {

ko.applyBindings(viewModel);

});

$("#sampleProperties").ejPropertiesPanel();

});

&lt;/script&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="Content2" runat="server" ContentPlaceHolderID="PropertySection"&gt;

&lt;div id="sampleProperties"&gt;

&lt;div class="row"&gt;

&lt;div class="col-md-3"&gt;

Current View

&lt;/div&gt;

&lt;div class="row"&gt;&lt;/div&gt;

&lt;div class="col-md-3"&gt;

&lt;input type="text" name="view" value="" style="width: 100px" data-bind="value: view" /&gt;

&lt;/div&gt;

&lt;div class="row"&gt;&lt;/div&gt;

&lt;/div&gt;

&lt;div class="row"&gt;

&lt;div class="col-md-3"&gt;

Current Date

&lt;/div&gt;

&lt;div class="col-md-3"&gt;&lt;/div&gt;

&lt;div class="col-md-3"&gt;

&lt;input id="datepick" data-bind="ejDatePicker: { value: date, width: '107px' }" /&gt;

&lt;/div&gt;

&lt;div class="col-md-3"&gt;&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="styleSection" ContentPlaceHolderID="StyleSection" runat="server"&gt;

&lt;style type="text/css"&gt;

b {

white-space: nowrap;

}

&lt;/style&gt;

&lt;/asp:Content&gt;



Output of the above code example is as follows.

{ ![](MVVM_images/MVVM_img3.png) | markdownify }
{:.image }
Figure 134: Schedule with Knockout Binding

