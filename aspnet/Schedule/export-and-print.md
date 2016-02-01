---
title: Export, import and print the Schedule with its appointments	
description: Export-Import/Print the complete Scheduler or specific appointment alone
platform: aspnet
control: schedule
documentation: ug
keywords: export, import, print 
---
# Export and Print

## Export Appointments

The Appointments can be exported as a whole collection or else a single appointment alone can be exported from the Scheduler. By default, the appointments are exported to .ics format which can then be imported and used in any of the other external calendars.

### Single Appointment Exporting

A single appointment can be exported by making use of its Id. You can achieve this functionality by making use of an `exportSchedule` method by passing the id of an appointment to export as one of its parameter. 

It can also be achieved in another way by enabling the context menu settings and then adding a custom menu option for export appointment functionality. When right clicked on an appointment, and **export Appointment** option is chosen, the exporting functionality can be handled through the `MenuItemClick` event, within which the **exportSchedule** method should be defined with the following parameters,

* Action name (to be called in the server-side)
* Server Event (optional)
* Appointment Id (mandatory for single Appointment exporting)

The following code example shows the way to export single appointment from the Scheduler.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" CurrentView="Month" CurrentDate="5/2/2014" OnServerExportICS="Schedule1_ExportICS" MenuItemClick="onMenuItemClick">
    <ContextMenuSettings Enable="true">
        <MenuItems>
            <AppointmentCollection>
                <ej:Appointment Id="open" Text="Open Appointment" />
                <ej:Appointment Id="delete" Text="Delete Appointment" />
                <ej:Appointment Id="exportApp" Text="Export Appointment" />
            </AppointmentCollection>
        </MenuItems>
    </ContextMenuSettings>
    <AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords"></asp:ObjectDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        // This function executes, when any of the menu options are clicked in the context menu
        function onMenuItemClick(args) {
            if (args.events.ID == "exportApp") {
                var obj = $("#Schedule1").data("ejSchedule");
                // exportSchedule() method will send a post to the server-side to call a specified action.
                obj.exportSchedule(null, "ExportICS", args.targetInfo.ID);
            }
        }
    </script>
</asp:Content>

{% endhighlight %}

N> The Id value of the appointment passed in the above code example can be retrieved in the server-side action through Request.Form["AppointmentId"], as the id passed from the script is stored as hidden value in the input field of the form under this name internally.

### Exporting all Appointments

To export the entire appointments, the same `exportSchedule` method can be used without passing the id value to its parameter list. To achieve this, keep an individual button to export, and when it is clicked - the Scheduler can be allowed to export all the appointments.

The following code example depicts the way to export all the Scheduler appointments as a whole.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" CurrentView="Month" CurrentDate="5/2/2014" OnServerExportICS="Schedule1_ExportICS">
    <AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

 <asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords"></asp:ObjectDataSource>

<!-- Button div for Export Option-->
<ej:Button ClientIDMode="Static" Type="Button" ID="exportFile" Height="30px" Width="60px" Text="Export" runat="server" ShowRoundedCorner="true" ClientSideOnClick="onExportClick"></ej:Button>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        // Clicking on the export button will call this method
        function onExportClick(Args) {
            var obj = $("#Schedule1").data("ejSchedule");
            // Calls the server-side action ExportToICS
            obj.exportSchedule(null, "ExportICS", null);
        }
    </script>
</asp:Content>

{% endhighlight %}

The server-side action **ExportICS** contains the following code example to export the Scheduler appointments.

{% highlight c# %}

public void ExportICS(FormCollection form)
{
	IEnumerable data;
	string JSONModel = Request.Form["ScheduleModel"];
	var model = JsonConvert.DeserializeObject<Dictionary<string, object>>(JSONModel);
	var Id = Request.Form["AppointmentId"];
	if(Id != null)
		// To export single appointment
		data = db.DefaultSchedules.Where(app => app.Id.ToString() == Id.ToString()).ToList();
	else
		// To export all the appointments
		data = db.DefaultSchedules.ToList();
	ScheduleExport obj = new ScheduleExport(model, data);
}

{% endhighlight %}

## Print

Two types of Print options are available – either to print the entire Scheduler layout including all the appointments in it or else to print any particular appointment alone. The public method `print` is used to print the entire Scheduler.

### Print the Scheduler

The following code example shows the way to print the entire Scheduler, by keeping an extra button in a page – on which clicking the button will print the entire Scheduler.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="800px" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<!--Button div for Print Option-->
<ej:Button ClientIDMode="Static" Type="Button" ID="print" Height="30px" Width="60px" Text="Print" runat="server" ShowRoundedCorner="true" ClientSideOnClick="onPrint"></ej:Button>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        function onPrint() {
            $("#Schedule1").find("tr.e-scheduleheader td").first().append($("#print"));
                var obj = $("#Schedule1").data("ejSchedule");
                obj.print();
        } 
    </script>
</asp:Content>

{% endhighlight %}

### Printing specific appointments

To print a particular appointment, the context menu **print** option can be used. The print option is handled internally by default, so that when an appointment is right clicked – choosing print option from the context menu that pops-out will automatically print that appointment.

N> To handle this functionality, the context menu settings needs to be enabled with print option added to the appointment items.

The following code example depicts the way to print a particular appointment.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="800px" CurrentDate="5/2/2014">
        <ContextMenuSettings Enable="true">
            <MenuItems>
                <AppointmentCollection>
                    <ej:Appointment Id="open" Text="Open Appointment" />
                    <ej:Appointment Id="delete" Text="Delete Appointment" />
                    <ej:Appointment Id="print" Text="Print Appointment" />
                </AppointmentCollection>
            </MenuItems>
        </ContextMenuSettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

## Import Appointments

To Import appointments to the Scheduler, server-side method `renderingImportAppointments` can be used which is depicted in the following code example.

The following code example depicts the way to import appointments for scheduler control.

{% highlight html %}

<asp:Button ID="Upload" runat="server" OnClick="Upload_Click" Text="Import" />
<div>
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" CurrentView="Month" CurrentDate="5/2/2014">
    <AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>
    </div>
    <asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords">
    </asp:ObjectDataSource>
</asp:Content>

{% endhighlight %}

The server-side code example to import the Scheduler appointments are as follows.

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class ScheduleICSImport : System.Web.UI.Page
    {

        ScheduleAppointmentsObjDatum data = new ScheduleAppointmentsObjDatum();
        protected void Upload_Click(object sender, EventArgs e)
        {
            string txt = "FilePath/iCalender.ics";
            ScheduleImport importApps = new ScheduleImport();
            var app = importApps.renderingImportAppointments(txt);
            var records = data.GetRecords();
            int maxID = Convert.ToInt32(records.Max(x => x.ID));
            List<ScheduleAppointmentsObjData> list = new List<ScheduleAppointmentsObjData>();
            for (var i = 0; i < app.Count; i++)
            {
                int ID = maxID + 1;
                ScheduleAppointmentsObjData row = new ScheduleAppointmentsObjData(ID, app[i].Subject, app[i].Location, app[i].StartTime, app[i].EndTime, app[i].Description, null, null, app[i].Recurrence, null, null, app[i].AppointmentCategorize, null, app[i].AllDay, null, null, app[i].RecurrenceRules,null,null);
                records.Add(row);
            }
            this.Schedule1.AppointmentSettings.DataSource = records;
        }
    }
}

{% endhighlight %}