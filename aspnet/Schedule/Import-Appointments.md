---
layout: post
title: Import-Appointments
description: import appointments
platform: aspnet
control: Schedule
documentation: ug
---

## Import Appointments

* With this feature, you can import the appointments from the .ics file into the Schedule control. ICS files that are generated from the Outlook, Google calendar and the exported files from the Syncfusion Schedule can be easily imported into the Schedule control. 
* Generally, the import functionality is achieved by using the server-side method renderingImportAppointments that takes the path of an ics file as its parameter. This method can be accessed through the object of the ScheduleImport class. You can dynamically choose the ics files to be imported into the Schedule control by using the upload box to select the ics file from the specific location. 
* Importing can be achieved by using the following code example in MVC and ASP. It is not applicable for JS, as it is done through server-side.



<table>
<tr>
<td>
[ASPX]// Upload box to dynamically import the ICS files from any of the system location&lt;ej:UploadBox ID="fileUpload1" runat="server" Height="30" ExtensionsAllow=".ics" SaveUrl="saveFiles.ashx" RemoveUrl="removeFiles.ashx" AutoUpload="true" ShowFileDetails="false" OnComplete="fileUpload1_Complete"&gt;&lt;UploadBoxButtonText Browse="Import ICS file" /&gt;&lt;/ej:UploadBox&gt;&lt;ej:Schedule runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" CurrentView="Month" CurrentDate="5/2/2014"&gt;&lt;AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description"/&gt;&lt;/ej:Schedule&gt;&lt;asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords"&gt;&lt;/asp:ObjectDataSource&gt;&lt;%--Script section-- %&gt;&lt;asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection"&gt;&lt;script type="text/javascript"&gt;$(document).ready(function () {$("#Schedule1").find("tr.e-scheduleheader td").first().append($("#fileUpload1"));});&lt;/script&gt;&lt;/asp:Content&gt;&lt;%--Styles section-- %&gt;&lt;asp:Content ID="styleSection" ContentPlaceHolderID="StyleSection" runat="server"&gt;&lt;style type="text/css"&gt;#fileUpload1{margin-right: 20px;margin-top: 10px;float: right;}#fileUpload1 .e-selectpart{padding: 3px 10px;}&lt;/style&gt;&lt;/asp:Content&gt;</td></tr>
<tr>
<td>
[ASPX.CS]ScheduleAppointmentsObjDatum data = new ScheduleAppointmentsObjDatum();protected void Page_Load(object sender, EventArgs e){this.Schedule1.AppointmentSettings.DataSource = data.GetRecords();}// On successful completion of file upload, import the appointments into the schedule controlprotected void fileUpload1_Complete(object sender, Syncfusion.JavaScript.Web.UploadBoxCompleteEventArgs e){string txt = HttpContext.Current.Server.MapPath("uploadfiles");txt = txt + "\\" + e.Name;// Create an object of the class ScheduleImportScheduleImport importApps = new ScheduleImport();// Access the method to import the ics file appointments into schedule control through the object created above.var app = importApps.renderingImportAppointments(txt);var records = data.GetRecords();int maxID = Convert.ToInt32(records.Max(x => x.ID));List<ScheduleAppointmentsObjData> list = new List<ScheduleAppointmentsObjData>();for (var i = 0; i < app.Count; i++){int ID = maxID + 1;ScheduleAppointmentsObjData row = new ScheduleAppointmentsObjData(ID, app[i].Subject, app[i].Location, app[i].StartTime, app[i].EndTime, app[i].Description, null, null, app[i].Recurrence, null, null, app[i].AppointmentCategorize, null, app[i].AllDay, null, null, app[i].RecurrenceRules);records.Add(row);}this.Schedule1.AppointmentSettings.DataSource = records;}</td></tr>
</table>


* Add the file “SaveFiles.ashx” in your project that contains the code example of the uploadbox to save the uploaded files into a specified folder.

[saveFiles.ashx]



public class SaveFiles : IHttpHandler

{

//To Save the uploaded files into corresponding folder

public void ProcessRequest(HttpContext context)

{

string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

if (!Directory.Exists(targetFolder))

{

Directory.CreateDirectory(targetFolder);

}

var request = context.Request;

HttpFileCollection uploadedFiles = context.Request.Files;

if (uploadedFiles != null && uploadedFiles.Count > 0)

{

for (int i = 0; i < uploadedFiles.Count; i++)

{

string fileName = uploadedFiles[i].FileName;

int indx = fileName.LastIndexOf("\\");

if (indx > -1)

{

fileName = fileName.Substring(indx + 1);

}

uploadedFiles[i].SaveAs(targetFolder + "\\" + fileName);

}

}

else

{



}

}



public bool IsReusable

{

get

{

return false;

}

}

}



* Also, add the file “RemoveFiles.ashx” in your project that contains the code example of uploadbox to remove the uploaded files. 

[removeFiles.ashx]



public class RemoveFiles : IHttpHandler

{

//Code to Remove the uploaded ics files

public void ProcessRequest(HttpContext context)

{

var s = context.Request.Params;

string fileName = s["fileNames"];

string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

if (!Directory.Exists(targetFolder))

{

Directory.CreateDirectory(targetFolder);

}

var physicalPath = targetFolder + "\\" + fileName;

if (System.IO.File.Exists(physicalPath))

{

System.IO.File.Delete(physicalPath);

}

}

public bool IsReusable

{

get

{

return false;

}

}

}





* Execute the above code. Now, click on the browse button. 
* It displays a window to choose the ics files which is to be uploaded into the Schedule control as illustrated in the following screenshot. 
* Choose the file and click “Open” to imports the selected file into your Schedule control.

{ ![](Import-Appointments_images/Import-Appointments_img1.png) | markdownify }
{:.image }




{ ![](Import-Appointments_images/Import-Appointments_img2.png) | markdownify }
{:.image }




* [Click here](http://asp.syncfusion.com/demos/web/schedule/scheduleicsexport.aspx) to see the__working of__Import and Export Appointments.



