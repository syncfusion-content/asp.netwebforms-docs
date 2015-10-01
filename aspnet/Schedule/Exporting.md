---
layout: post
title: Exporting | Schedule | ASP.NET Webforms | Syncfusion
description: exporting
platform: aspnet
control: Schedule
documentation: ug
---

# Exporting

* Schedule appointments is exported to ISC file format. Therefore, it is possible to import the appointments to Microsoft outlook. Exporting can be achieved by the public method export. It contains two argument. 
* The first argument states that for MVC, the action name that is to be redirected is mentioned and for ASP it is set as null. 
* The second argument is for exporting type. Currently there is only ICSExport. For MVC project it is not required to pass this argument. You can achieve exporting by using the following code example in MVC and in ASP.

{% highlight text %}

Important: Exporting feature is not applicable for JS as it is performed in Server side.

{% endhighlight %}

{% tabs %}


{% highlight html %}

<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

<span class="sampleName">Schedule / Import & Export</span>

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<ej:Button ClientIDMode="Static" ID="exportFile" Height="32px" Width="60px" Text="Export" runat="server" ShowRoundedCorner="true" ClientSideOnClick="onExportClick">

</ej:Button>

<div>

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" CurrentView="Month" CurrentDate="5/2/2014" OnServerExportICS="Schedule1_ExportICS" MenuItemClick="onMenuItemClick">

<AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>

</ej:Schedule>

</div>
<asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords">

</asp:ObjectDataSource>
</asp:Content>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">

<script type="text/javascript">

$(function () {

$("#sampleProperties").ejPropertiesPanel();

$("#Schedule1").find("tr.e-scheduleheader td").first().append($("#exportFile"));});

function onExportClick(Args) 
{

var obj = $("#Schedule1").data("ejSchedule");

obj.exportSchedule(null, "exportICS", null);

}

</script>

</asp:Content>

<asp:Content ID="StyleContent" ContentPlaceHolderID="StyleSection" runat="server">

<style type="text/css">

#exportFile
{
border: 1px solid #bbbcbb;
border-radius: 0 6px 6px 0;
float: right;
margin-right: 20px;
margin-top: 8px;
padding-top:5px;
}

</style>

</asp:Content>

{% endhighlight %}

{% highlight C# %}

using Newtonsoft.Json;

using Syncfusion.EJ.Export;

// the above two references are important for export the schedule.

public partial class ScheduleICSExport : System.Web.UI.Page
{
ScheduleAppointmentsObjDatum data = new ScheduleAppointmentsObjDatum();

protected void Page_Load(object sender, EventArgs e)
{
this.Schedule1.AppointmentSettings.DataSource = data.GetRecords();
}

// method for server event “OnServerExportICS”

protected void Schedule1_ExportICS(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
{
IEnumerable datum = data.GetRecords();

var model = JsonConvert.DeserializeObject<Dictionary<string, object>>(e.Arguments["model"].ToString());

// method for ICS File export has been called.ScheduleExport obj = new ScheduleExport(model, datum);}

}

{% endhighlight %}

{% endtabs %}

Execute the above code to render the following output.

![](Exporting_images/Exporting_img1.png)

Schedule with Appointment export feature
{:.caption }
