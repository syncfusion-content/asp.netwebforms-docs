---
title: Export, import and print the Schedule with its appointments	
description: Export-Import/Print the complete Scheduler or specific appointment alone using the Syncfusion ASP.NET Web Forms Schedule control.
platform: aspnet
control: schedule
documentation: ug
keywords: export, import, print 
---
# Export and Print

## Export Appointments to ICS file

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

To export the entire Scheduler appointments, the same `exportSchedule` method can be used without passing the id value to its parameter list. To achieve this, keep an individual button to export, and when it is clicked - the Scheduler can be allowed to export all the appointments.

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

## PDF Export

Scheduler supports exporting it along with all its appointments in PDF format, for which the same `exportSchedule` method can be used without passing any id value to its parameter list. To achieve this, keep an individual button to export and when it is clicked, the Scheduler with appointments can be allowed to export as PDF.

The following code example depicts the way to export the Scheduler with appointments in PDF format.

{% highlight html %}
 
 <asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">
    <ej:Button ClientIDMode="Static" Type="Button" ID="exportFile" runat="server" Text="Export" ClientSideOnClick="onExportClick"></ej:Button>
        <div>
<ej:Schedule OnServerExportPDF="Schedule1_OnServerExportPDF" ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" CurrentView="Workweek">
    <Resources>
        <ej:Resources Field="RoomId" Name="Rooms" Title="Room" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text" GroupId="groupId">
            </ResourceSettings>
        </ej:Resources>
         
    </Resources>
    <Group Resources="Rooms,Owners"/>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="RoomId,OwnerId"/>
</ej:Schedule>
    </div>
    <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>
</asp:Content>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        $(document).ready(function () {
            $("#Schedule1").find("tr.e-scheduleheader td").first().append($("#exportFile"));
        });
        function onExportClick(args) {
            var obj = $("#Schedule1").data("ejSchedule");
            obj.exportSchedule(null, "exportPDF", null);
        }
    </script>
</asp:Content>
<asp:Content ID="StyleContent" ContentPlaceHolderID="StyleSection" runat="server">
      <style type="text/css">
        #exportFile
        {
           border: 1px solid #bbbcbb;
           border-radius: 6px;
           float: right;
           margin-right: 20px;
           margin-top: 8px;
           padding-top:5px;
           box-sizing:border-box;
        }
    </style>
</asp:Content>
 
 {% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class PDFExport : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<WebSampleBrowser.Schedule.multipleresource.Rooms> owner = new List<WebSampleBrowser.Schedule.multipleresource.Rooms>();
            List<WebSampleBrowser.Schedule.multipleresource.Rooms> rooms = new List<WebSampleBrowser.Schedule.multipleresource.Rooms>();
            rooms.Add(new WebSampleBrowser.Schedule.multipleresource.Rooms { text = "Room1", id = "1", color = "#cb6bb2" });
            rooms.Add(new WebSampleBrowser.Schedule.multipleresource.Rooms { text = "Room2", id = "2", color = "#56ca85" });

            owner.Add(new WebSampleBrowser.Schedule.multipleresource.Rooms { text = "Nancy", id = "1", groupId = "1", color = "#ffaa00" });
            owner.Add(new WebSampleBrowser.Schedule.multipleresource.Rooms { text = "Steven", id = "3", groupId = "2", color = "#f8a398" });
            owner.Add(new WebSampleBrowser.Schedule.multipleresource.Rooms { text = "Michael", id = "5", groupId = "1", color = "#7499e1" });

            Schedule1.Resources[0].ResourceSettings.DataSource = rooms;
            Schedule1.Resources[1].ResourceSettings.DataSource = owner;
        }
        protected void Schedule1_OnServerExportPDF(object sender, ScheduleEventArgs e)
        {
            JavaScriptSerializer serializer = new JavaScriptSerializer();
            SchedulePDFExport convert = new SchedulePDFExport();
            // Here calling the public method to convert the model values to ScheduleProperties type from string type
            ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(e.Arguments["model"].ToString());
            // Here converting the schedule appointments data into enumerable object by deserializing
            IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(e.Arguments["processedApp"].ToString(), typeof(IEnumerable));
            PdfExport exp = new PdfExport();
            PdfPageSettings pageSettings = new PdfPageSettings(50f);
            pageSettings.Orientation = PdfPageOrientation.Landscape;
            // Here passing the theme values from enum collection
            PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, e.Arguments["locale"], pageSettings);
            document.Save("Schedule.pdf", Response, HttpReadType.Save);
        }
    }
}

{% endhighlight %}

N> To pass the theme value as a string instead of the enum value, refer to the following code example of passing the string type theme value.
{% highlight c# %}
    PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, "flat-saffron",e.Arguments["locale"]);
{% endhighlight %}

### Setting Page Options:

It is possible to set/change the PDF page settings such as size, margins (left, right, top and bottom), transition, and rotate angle and header/footer values by passing the page settings and page document template object values into the export method. 

#### Page Settings:

You can set/apply the following page property values to the PDF file before exporting it with the Scheduler by using the `PdfPageSettings` object. 

* Page Size
* Orientation
* Margins (Left, Right, Top, Bottom)
* Transition (Direction, Dimension, Duration, Motion, PageDuration, Scale, Style)
* Rotate (RotateAngle0, RotateAngle90, RotateAngle180, RotateAngle270)
* Height
* Width

To apply the above page setting values, you need to create an object for the `PdfPageSettings` class. Then, you can assign the values to the available properties within it such as Size = PdfPageSize.A3, Orientation = PdfPageOrientation.Landscape and so on. Once done, pass this object into the export method which will set these page settings values to the PDF file before exporting it. Refer to the following code example (server-side) to set/change the page settings values.

{% highlight c# %}
        protected void Schedule1_OnServerExportPDF(object sender, ScheduleEventArgs e)
        {

            JavaScriptSerializer serializer = new JavaScriptSerializer();
            SchedulePDFExport convert= new SchedulePDFExport();
            ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(e.Arguments["model"].ToString()); // Here calling the public method to convert the model values to ScheduleProperties type from string type

            IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(e.Arguments["processedApp"].ToString(), typeof(IEnumerable)); // Here deserialize the appointments to enumerable object

            PdfExport exp = new PdfExport();

            // Here the 50f is the default value for the margins. If you are not assigning any separate values like Margins.Left = 15 means 50f value will be setting to all the Margin properties.
            PdfPageSettings pageSettings = new PdfPageSettings(50f);  

            // Here you can assign the PdfPageSize enum value (ex: A3, A4)
            pageSettings.Size = PdfPageSize.A3;  

            // Here Landscape value assigned to the orientation. You can set either Landscape/Portrait for this Orientation property
            pageSettings.Orientation = PdfPageOrientation.Landscape; 

            // Here assigned different values for the margins 
            pageSettings.Margins.Left = 15;

            pageSettings.Margins.Right = 15;

            pageSettings.Margins.Top = 20;

            pageSettings.Margins.Bottom = 20;

            // Here assigned the Transition Direction as BottomToTop. You can also set any of the Transition values to this property

            pageSettings.Transition.Direction= PdfTransitionDirection.BottomToTop;

            // Here assigned the Rotate Angle as RotateAngle180. You can also set any of the Rotate values to this property
            pageSettings.Rotate = PdfPageRotateAngle.RotateAngle180;

            // Here passing the page settings object value into the export method.

            PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, e.Arguments["locale"], pageSettings);
            document.Save("Schedule.pdf", Response, HttpReadType.Save);
        }
{% endhighlight %}

#### Header/Footer Settings:

You can also set the header and footer options to the PDF page before it is being exported, by passing the `PDFDocumentTemplate` object values as mentioned in the following code example. 

{% highlight c# %}
        protected void Schedule1_OnServerExportPDF(object sender, ScheduleEventArgs e)
        {
            JavaScriptSerializer serializer = new JavaScriptSerializer();
            SchedulePDFExport convert= new SchedulePDFExport();
            ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(e.Arguments["model"].ToString()); // Here calling the public method to convert the model values to ScheduleProperties type from string type

            IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(e.Arguments["processedApp"].ToString(), typeof(IEnumerable)); // Here deserialize the appointments to enumerable object
            PdfExport exp = new PdfExport();
            PdfDocument document = new PdfDocument();
            PdfPage pdfPage = document.Pages.Add();

            //Create a header and draw the string.
            // Here the bounds value is used to store the position/axis value, where the header and footer content to be displayed
            RectangleF bounds = new RectangleF(0, 0, document.Pages[0].GetClientSize().Width, 50);

            // Creating object for the PdfPageTemplateElement
            PdfPageTemplateElement header = new PdfPageTemplateElement(bounds);

            // Here setting the font style and color to display the header/footer content

            PdfSolidBrush brush = new PdfSolidBrush(Color.Gray);

            PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 6, PdfFontStyle.Bold);

            PdfStringFormat format = new PdfStringFormat();

            format.Alignment = PdfTextAlignment.Center;

            format.LineAlignment = PdfVerticalAlignment.Middle;

            header.Graphics.DrawString("Schedule", font, brush, new RectangleF(0, 18, header.Width, header.Height), format);

            //Create a Page template that can be used as footer (here creating template to display the page number).
            PdfPageTemplateElement footer = new PdfPageTemplateElement(bounds);

            //Create page number field.
            PdfPageNumberField pageNumber = new PdfPageNumberField(font, brush);

            //Create page count field.
            PdfPageCountField count = new PdfPageCountField(font, brush);

            //Add the fields in composite fields.
            PdfCompositeField compositeField = new PdfCompositeField(font, brush, "Page {0} of {1}", pageNumber, count);

            compositeField.Bounds = footer.Bounds;

            //Draw the composite field in footer.
            compositeField.Draw(footer.Graphics, new PointF(470, 40));

            PdfDocumentTemplate headerFooterTemplate = new PdfDocumentTemplate();
            
            //Here assigning the header template value to the PdfDocumentTemplate Object.
            headerFooterTemplate.Top = header; 

            //Here assigning the footer template value to the PdfDocumentTemplate Object.
            headerFooterTemplate.Bottom = footer;

            //Here passing the PdfDocumentTemplate Object value into the export method.

            document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, e.Arguments["locale"], headerFooterTemplate);

            document.Save("Schedule.pdf", Response, HttpReadType.Save);
        }

{% endhighlight %}

N>The header and footer values can be passed to the PDF file only through the template option. In the above mentioned code example, the template has been written with the text “Schedule” to display it as the header text and the page number (ex: Page 1 of 2) has been displayed in the footer part. 

It is also possible to pass both the `PageSettings` and header/footer template objects in the export method altogether to apply the page settings as well as the header and footer options to the PDF file which can be referred from the following code example,

{% highlight c# %}
        public ActionResult ExportAsPDF(string scheduleModel)
        {
            //Here add the code example of both the page settings and header/footer values settings.
            
            //Then pass both PdfPageSettings and PdfDocumentTemplate object into the export method.            
            
            document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, e.Arguments["locale"], pageSettings, headerFooterTemplate);
            document.Save("Schedule.pdf", Response, HttpReadType.Save);
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

### Printing Specific Appointments

To print a particular appointment, either the default context menu **print** option can be used or else the `print` method can be used by passing the id of the appointment to be printed as its argument.

#### Using Context Menu

Here, the print action is handled internally by default, so that when an appointment is right clicked – choosing print option from the context menu that pops-out will automatically print that particular appointment.

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

#### Using print() method

The public method `print` needs to be used here by passing the appointment object as its argument, that needs to be printed.

For example, here the below code example depicts the way to print the particular appointment programmatically by calling the **print** function within the `AppointmentClick` event, which triggers whenever the user clicks on an appointment.

{% highlight html %}

 <!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="800px" CurrentDate="5/2/2014" AppointmentClick="onAppointmentClick">
        <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" />
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
        SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
<script type="text/javascript">
        function onAppointmentClick(args) {
            var schObj = $("#Schedule1").data("ejSchedule");
            schObj.print(args.appointment);
        }
</script>

{% endhighlight %}
## Import Appointments

To import appointments into the Scheduler, server-side method `renderingImportAppointments` needs to be used, which returns the list of appointments retrieved from the specified file path.

Refer the following code example to import the appointments into Scheduler.

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

The server-side action **ImportICSFile** contains the following code example to import the Scheduler appointments. 

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