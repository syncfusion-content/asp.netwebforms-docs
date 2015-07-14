---
layout: post
title: Template
description: template
platform: aspnet
control: Schedule
documentation: ug
---

## Template

### Appointment Template

* The appointments are provided with rich template support, so that the customizations are done easily. You can add the appointment template to the Schedule control as follows.


[ASP]



&lt;asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server"&gt;

<span class="sampleName">Schedule / Template</span>

&lt;/asp:Content&gt;



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div&gt;

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentView="Month" Width="100%" Height="525px" AppointmentTemplateId="#MyTemplate"

CurrentDate="5/2/2014">

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

&lt;%--appointment template definition-- %&gt;

&lt;script id="MyTemplate" type="text/x-jsrender"&gt;

&lt;div style="height: 100%"&gt;

&lt;div style="float: left; width: 24px;"&gt;

{{:~format(StartTime)}}

&lt;/div&gt;

&lt;div&gt;

&lt;div&gt;{{:Subject}}&lt;/div&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;/script&gt;

&lt;script type="text/javascript"&gt;

//the below function selects the images to be displayed on the appointments based on the day of the appointment’s startTime.

//Note: The below used images should be present in a separate images folder, so that it will be referred properly.



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



* The output for the above code is as follows that displays the appointment with the template defined for it.

{ ![](Template_images/Template_img1.png) | markdownify }
{:.image }


      _Figure_ _82__: schedule with template._



### ResourceHeader Template

* The resources are provided with rich template support, so that the customizations are done easily. You can add the resource header template to the Schedule control as follows.



<table>
<tr>
<td>
[ASP]&lt;ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" ResourceHeaderTemplateId="#resourceHeaderTemplateId"&gt;&lt;Group Resources="Owners"/&gt;&lt;%--Resource data collection-- %&gt;&lt;Resources&gt;&lt;%--Enable the multiple selection of resources in the appointment window-- %&gt;&lt;ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true"&gt;&lt;ResourceSettings Color="color" Id="id" Text="text"&gt;&lt;/ResourceSettings&gt;&lt;/ej:Resources&gt;&lt;/Resources&gt;&lt;AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description" ResourceFields="OwnerId"/&gt;&lt;/ej:Schedule&gt;&lt;asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="&lt;%$ ConnectionStrings: ScheduleConnectionString %&gt;"SelectCommand="SELECT * FROM [MultipleResource]">&lt;/asp:SqlDataSource&gt;// resourceHeader template definition&lt;script type="text/x-jsrender" id="resourceHeaderTemplateId"&gt;&lt;img style="width: 40px; height: 40px" src=".../images/schedule/{{:id}}.png" alt="{{:id}}" /&gt;  &lt;/script&gt;</td></tr>
<tr>
<td>
[ASPX.CS]namespace WebSampleBrowser.Schedule{public partial class multipleresource : System.Web.UI.Page{protected void Page_Load(object sender, EventArgs e){List<Rooms> owners = new List<Rooms>();owners.Add(new Rooms { text = "Andrew", id = "1", color = "#f8a398" });owners.Add(new Rooms { text = "Cruise", id = "3", color = "#56ca85" });owners.Add(new Rooms { text = "Jerry", id = "5", color = "#51a0ed" });Schedule1.Resources[0].ResourceSettings.DataSource = owners;}public class Rooms{public string text { set; get; }public string id { set; get; }public string color { set; get; }}}}</td></tr>
</table>


Important: The above used images should be present in a separate images folder, so that it will be referred properly.The images name should be saved with id as same as given in the resourceSettings inorder to set unqiue images to all resources.



The output of the above code looks as follows.



{ ![C:/Users/karthigeyan/Desktop/a.png](Template_images/Template_img2.png) | markdownify }
{:.image }














