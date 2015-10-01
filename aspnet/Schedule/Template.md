---
layout: post
title: Template | Schedule | ASP.NET Webforms | Syncfusion
description: template
platform: aspnet
control: Schedule
documentation: ug
---

# Template

## Appointment Template

* The appointments are provided with rich template support, so that the customizations are done easily. You can add the appointment template to the Schedule control as follows.

{% highlight html %}




<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Template</span>

</asp:Content>



<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentView="Month" Width="100%" Height="525px" AppointmentTemplateId="#MyTemplate"

CurrentDate="5/2/2014">

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

<%--appointment template definition-- %>

<script id="MyTemplate" type="text/x-jsrender">

<div style="height: 100%">

<div style="float: left; width: 24px;">

{{:~format(StartTime)}}

</div>

<div>

<div>{{:Subject}}</div>

</div>

</div>

</script>

<script type="text/javascript">

//the below function selects the images to be displayed on the appointments based on the day of the appointment’s startTime.

//Note: The below used images should be present in a separate images folder, so that it will be referred properly.



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

* The output for the above code is as follows that displays the appointment with the template defined for it.

![](Template_images/Template_img1.png)

schedule with template.
{:.caption} 

## ResourceHeader Template

* The resources are provided with rich template support, so that the customizations are done easily. You can add the resource header template to the Schedule control as follows.

{% tabs %}

{% highlight html %}

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" ResourceHeaderTemplateId="#resourceHeaderTemplateId">

	<Group Resources="Owners"/><%--Resource data collection-- %>

	<Resources>

		<%--Enable the multiple selection of resources in the appointment window-- %>

		<ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">

			<ResourceSettings Color="color" Id="id" Text="text"> </ResourceSettings>
			
		</ej:Resources></Resources>

		<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description" ResourceFields="OwnerId"/>

		</ej:Schedule><asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"SelectCommand="SELECT * FROM [MultipleResource]">

		</asp:SqlDataSource>

		// resourceHeader template definition<script type="text/x-jsrender" id="resourceHeaderTemplateId">

		<img style="width: 40px; height: 40px" src=".../images/schedule/{{:id}}.png" alt="{{:id}}" />  

		</script>

{% endhighlight %}

{% highlight C# %}

namespace WebSampleBrowser.Schedule
{
public partial class multipleresource : System.Web.UI.Page
{
protected void Page_Load(object sender, EventArgs e)
{
List<Rooms> owners = new List<Rooms>();
owners.Add(new Rooms { text = "Andrew", id = "1", color = "#f8a398" });
owners.Add(new Rooms { text = "Cruise", id = "3", color = "#56ca85" });
owners.Add(new Rooms { text = "Jerry", id = "5", color = "#51a0ed" });
Schedule1.Resources[0].ResourceSettings.DataSource = owners;
}
public class Rooms
{
public string text { set; get; }
public string id { set; get; }
public string color { set; get; }
}
}

{% endhighlight %}

{% endtabs %}

{% highlight text %}

Important: The above used images should be present in a separate images folder, so that it will be referred properly.The images name should be saved with id as same as given in the resourceSettings inorder to set unqiue images to all resources.

{% endhighlight %}

The output of the above code looks as follows.

![C:/Users/karthigeyan/Desktop/a.png](Template_images/Template_img2.png)