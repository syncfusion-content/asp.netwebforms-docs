---
title: Data binding with Schedule	
description: Databinding is used to show the different binding of adaptor section using Syncfusion ASP.NET Web Forms Schedule component.
platform: aspnet
control: schedule
documentation: ug
keywords: data binding, local data, remote data 
---
# Data Binding

## Appointment Fields

The below listed names are the appointment fields which holds the appropriate column names from the dataSource.

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Id<br/><br/></td><td>
Binds the <b>Id</b> field name for indexing and performing CRUD operation on the appointments. It’s optional.<br/><br/></td></tr>
<tr>
<td>
StartTime<br/><br/></td><td>
Binds the appointment start time field name which is <b>mandatory</b>and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
StartTimeZone<br/><br/></td><td>
Binds the name of the start timezone field in the dataSource and also its related validation rules. If the <b>StartTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
EndTime<br/><br/></td><td>
Binds the appointment end time field name which is <b>mandatory</b>and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
EndTimeZone<br/><br/></td><td>
Binds the name of the end timezone field in the dataSource and also its related validation rules. If the <b>EndTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
Subject<br/><br/></td><td>
Binds the appointment subject field name which holds the summary of the appointment and also its related validation rules. <br/><br/></td></tr>
<tr>
<td>
Location<br/><br/></td><td>
Binds the name of the location field and also its related validation rules. It indicates the appointment location/occurrence place. This field needs to be bind to the Scheduler, when an API <b>ShowLocationField</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
Description<br/><br/></td><td>
Binds the appointment description field name and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
AllDay<br/><br/></td><td>
Binds the name of the allDay field. It accepts the <b>boolean</b> value and indicates whether the appointment is an all-day appointment or not.<br/><br/></td></tr>
<tr>
<td>
Categorize<br/><br/></td><td>
Binds the name of the categorize field and also its related validation rules. It indicates the category or status value (red categorize, green, yellow and so on). <br/><br/></td></tr>
<tr>
<td>
Priority<br/><br/></td><td>
Binds the name of the priority field and its related validation rules, which indicates the priority (high, low, medium and none) of the appointments. This field should be bind to the Scheduler, when <b>PrioritySettings.Enable</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
ResourceFields<br/><br/></td><td>
Binds one or more fields in the resource collection. It maps the resource field names with the appointments, denoting to which resource the appointments actually belongs.<br/><br/></td></tr>
<tr>
<td>
Recurrence<br/><br/></td><td>
Binds the name of the recurrence field. It accepts the <b>boolean</b> value and indicates whether the appointment is a recurrence appointment or not.<br/><br/></td></tr>
<tr>
<td>
RecurrenceRule<br/><br/></td><td>
Binds the name of the recurrenceRule field. It holds the recurrence pattern associated with the appointments.<br/><br/></td></tr>
<tr>
<td>
RecurrenceId<br/><br/></td><td>
Binds the recurrence Id field which acts as a parent id for Scheduler recurrence appointments.<br/><br/></td></tr>
<tr>
<td>
RecurrenceExDate<br/><br/></td><td>
Binds the recurrence Exception field which accepts the recurrence Exception date values.<br/><br/></td></tr>
</table>

The below example depicts the appointment fields accepting the string type mapper fields,

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" ShowLocationField="true" CurrentDate="5/5/2014">
    <Group Resources="Owners" />
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <CategorizeSettings Enable="true"></CategorizeSettings>
    <PrioritySettings Enable="true"></PrioritySettings>
    <AppointmentSettings Id="Id" Subject="Subject" StartTime="StartTime" StartTimeZone="StartTimeZone" EndTime="EndTime" EndTimeZone="EndTimeZone" AllDay="AllDay" Description="Description" Location="Location" Priority="Priority" Categorize="Categorize" ResourceFields="OwnerId" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" RecurrenceId="RecurrenceId" RecurrenceExDate="RecurrenceExDate"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

N> In the above code example, SQL Datasource has been used and the table named "MultipleResource" is created with all the required Scheduler fields and appropriate values. The field names captioned within this table must be mapped properly with the Scheduler AppointmentSettings fields.

The below code defined in the aspx.cs page shows the list of resources to be assigned to the Scheduler from code behind.

{% highlight c# %}

        protected void Page_Load(object sender, EventArgs e)
        {
            List<Rooms> owners = new List<Rooms>();
            owners.Add(new Rooms { text = "Nancy", id = "1", color = "#f8a398" });
            owners.Add(new Rooms { text = "Steven", id = "3", color = "#56ca85" });
            owners.Add(new Rooms { text = "Michael", id = "5", color = "#51a0ed" });
            Schedule1.Resources[0].ResourceSettings.DataSource = owners;
        }
        public class Rooms
        {
            public string text { set; get; }
            public string id { set; get; }
            public string groupId { set; get; }
            public string color { set; get; }
        }

{% endhighlight %}

## Appointment Field Validation

It is possible to validate the required fields of the appointment window from client-side before submitting it, by adding appropriate validation rules to each of the fields. The appointment fields have been extended to accept both String and object type values. Therefore, in order to perform validations, it is necessary to specify object values for the appointment fields.    

Refer the appointment fields specified with validation rules from the following code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" ShowLocationField="true">
            <CategorizeSettings Enable="true">
            </CategorizeSettings>
            <AppointmentSettings Id="Id" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" />
        </ej:Schedule>
        
         <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
                SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
        
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        $(function () {
            $.validator.addMethod("customRule", function (value, element, options) {
                var expression = /^[a-zA-Z0-9- ]*$/;
                return expression.test(value);
            }, "Special character(s) not allowed in Location field");
        });
    </script>
</asp:Content>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class Validation : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            Schedule1.AppointmentSettings.Subject = new AppointmentSettings() { Field = "Subject", ValidationRules = new Dictionary<string, object>() { { "required", true } } };
            Schedule1.AppointmentSettings.Location = new AppointmentSettings() { Field = "Location", ValidationRules = new Dictionary<string, object>() { { "required", true }, { "customRule", "/^[a-zA-Z0-9- ]*$/" } } };
            Schedule1.AppointmentSettings.Description = new AppointmentSettings() { Field = "Description", ValidationRules = new Dictionary<string, object>() { { "required", true }, { "minlength", 5 }, { "maxlength", 500 } } };
            Schedule1.AppointmentSettings.Categorize = new AppointmentSettings() { Field = "Categorize", ValidationRules = new Dictionary<string, object>() { { "required", true } } };
        }
    }
}

{% endhighlight %}

## Binding to Object DataSource

Scheduler also supports binding the events data from Object datasource as depicted in the below code example.

**Example** - Object Data Binding

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="objectDataSource1" Width="100%" Height="525px" CurrentView="Month" CurrentDate="5/2/2014">
    <AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:ObjectDataSource ID="objectDataSource1" runat="server" TypeName="ScheduleAppointmentsObjDatum" SelectMethod="GetRecords">
    </asp:ObjectDataSource>

{% endhighlight %}

N> In the above code example, Object Datasource has been used and the class named "ScheduleAppointmentsObjDatum" is created with all the required Scheduler fields. The field names captioned within this class must be mapped properly with the Scheduler AppointmentSettings fields. The "GetRecords" method should also be defined on the code behind to retrieve the required data.

The class definition to be made on the code behind page is as follows,

{% highlight c# %}

public class ScheduleAppointmentsObjDatum
{

    [DataObjectMethod(DataObjectMethodType.Select)]
    public List<ScheduleAppointmentsObjData> GetRecords()
    {

        List<ScheduleAppointmentsObjData> list = new List<ScheduleAppointmentsObjData>();
        list.Add(new ScheduleAppointmentsObjData(100, "Bering Sea Gold", "chennai", "05/02/2014 09:00:00 AM", "05/02/2014 10:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=2;COUNT=10",null,null));
        list.Add(new ScheduleAppointmentsObjData(101, "Bering Sea Gold", "mum", "05/02/2014 04:00:00 AM", "05/02/2014 05:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(102, "Bering Sea Gold", "tiruchirapalli", "05/02/2014 04:00:00 PM", "05/02/2014 05:30:00 PM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(103, "What Happened Next?", "chennai", "05/04/2014 03:00:00 AM", "05/04/2014 04:30:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(104, "Bering Sea Gold", "tiruchirapalli", "05/04/2014 05:00:00 AM", "05/04/2014 05:40:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null,null));
        list.Add(new ScheduleAppointmentsObjData(105, "Daily Planet", "chennai", "05/03/2014 01:00:00 AM", "05/03/2014 02:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(106, "Alaska: The Last Frontier", "chennai", "05/03/2014 08:00:00 AM", "05/03/2014 09:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(107, "How It's Made", "chennai", "05/01/2014 06:00:00 AM", "05/01/2014 06:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15", null, null));
        list.Add(new ScheduleAppointmentsObjData(108, "Deadest Catch", "chennai", "05/03/2014 04:00:00 PM", "05/03/2014 05:00:00 PM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(109, "MayDay", "chennai", "04/30/2014 06:30:00 AM", "04/30/2014 07:30:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(110, "MoonShiners", "chennai", "05/02/2014 02:00:00 AM", "05/02/2014 02:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=1;COUNT=5", null, null));
        list.Add(new ScheduleAppointmentsObjData(111, "Close Encounters", "chennai", "04/30/2014 02:00:00 PM", "04/30/2014 03:00:00 PM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=MO,TH;INTERVAL=1;COUNT=5", null, null));
        list.Add(new ScheduleAppointmentsObjData(112, "Close Encounters", "mum", "04/30/2014 03:00:00 AM", "04/30/2014 03:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=WE;INTERVAL=1;COUNT=3", null, null));
        list.Add(new ScheduleAppointmentsObjData(113, "Highway Through Hell", "chennai", "05/01/2014 03:00:00 AM", "05/01/2014 07:00:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=2;COUNT=10", null, null));
        list.Add(new ScheduleAppointmentsObjData(114, "Moon Shiners", "chennai", "05/02/2014 04:20:00 AM", "05/02/2014 05:50:00 AM", "", "1", "", false, "", "", "", "", false, "", "", "", null, null));
        list.Add(new ScheduleAppointmentsObjData(115, "Cash Cab", "chennai", "04/30/2014 03:00:00 PM", "04/30/2014 04:30:00 PM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=1;COUNT=5", null, null));
        return list;

    }

}

[Serializable]
public class ScheduleAppointmentsObjData
{
    private int _id;
    private String _subject;
    private String _location;
    private String _startTime;
    private String _endTime;
    private String _description;
    private String _owner;
    private String _priority;
    private Boolean _recurrence;
    private String _recurrenceType;
    private String _recurrenceTypeCount;
    private String _remainderCategorize;
    private String _customStyle;
    private Boolean _allDay;
    private String _recurrenceStartDate;
    private String _recurrenceEndDate;
    private String _recurrenceRule;
    private String _startTimeZone;
    private String _endTimeZone;

    public ScheduleAppointmentsObjData()
    {
        
    }
    public ScheduleAppointmentsObjData(int _id, string _subject, string _location, string _startTime, string _endTime, string _description, string _owner, string _priority, bool _recurrence, string _recurrenceType, string _recurrenceTypeCount, string _remainderCategorize, string _customStyle, bool _allDay, string _recurrenceStartDate, string _recurrenceEndDate, string _recurrenceRule,string _startTimeZone,string _endTimeZone)
    {
        this._id = _id;
        this._subject = _subject;
        this._location = _location;
        this._startTime = _startTime;
        this._endTime = _endTime;
        this._description = _description;
        this._owner = _owner;
        this._priority = _priority;
        this._recurrence = _recurrence; ;
        this._recurrenceType = _recurrenceType;
        this._recurrenceTypeCount = _recurrenceTypeCount;
        this._remainderCategorize = _remainderCategorize;
        this._customStyle = _customStyle;
        this._allDay = _allDay;
        this._recurrenceStartDate = _recurrenceStartDate;
        this._recurrenceEndDate = _recurrenceEndDate;
        this._recurrenceRule = _recurrenceRule;
        this._startTimeZone = _startTimeZone;
        this._endTimeZone = _endTimeZone;
       
    }

    public int ID
    {
        get
        {
            return _id;
        }
        set
        {
            _id = value;
        }
    }

    public string Subject
    {
        get
        {
            return _subject;
        }
        set
        {
            _subject = value;
        }
    }
    public string Location
    {
        get
        {
            return _location;
        }
        set
        {
            _location = value;
        }
    }
    public string StartTime
    {
        get
        {
            return _startTime;
        }
        set
        {
            _startTime = value;
        }
    }
    public string EndTime
    {
        get
        {
            return _endTime;
        }
        set
        {
            _endTime = value;
        }
    }
    public string Description
    {
        get
        {
            return _description;
        }
        set
        {
            _description = value;
        }
    }
    public string Owner
    {
        get
        {
            return _owner;
        }
        set
        {
            _owner = value;
        }
    }
    public string Priority
    {
        get
        {
            return _priority;
        }
        set
        {
            _priority = value;
        }
    }
    public Boolean Recurrence
    {
        get
        {
            return _recurrence;
        }
        set
        {
            _recurrence = value;
        }
    }
    public string RecurrenceType
    {
        get
        {
            return _recurrenceType;
        }
        set
        {
            _recurrenceType = value;
        }
    }
    public string RecurrenceTypeCount
    {
        get
        {
            return _recurrenceTypeCount;
        }
        set
        {
            _recurrenceTypeCount = value;
        }
    }
    public string RemainderCategorize
    {
        get
        {
            return _remainderCategorize;
        }
        set
        {
            _remainderCategorize = value;
        }
    }
    public string CustomStyle
    {
        get
        {
            return _customStyle;
        }
        set
        {
            _customStyle = value;
        }
    }
    public Boolean AllDay
    {
        get
        {
            return _allDay;
        }
        set
        {
            _allDay = value;
        }
    }
    public string RecurrenceStartDate
    {
        get
        {
            return _recurrenceStartDate;
        }
        set
        {
            _recurrenceStartDate = value;
        }
    }
    public string RecurrenceEndDate
    {
        get
        {
            return _recurrenceEndDate;
        }
        set
        {
            _recurrenceEndDate = value;
        }
    }
    public string RecurrenceRule
    {
        get
        {
            return _recurrenceRule;
        }
        set
        {
            _recurrenceRule = value;
        }
    }
    public string StartTimeZone
    {
        get
        {
            return _startTimeZone;
        }
        set
        {
            _startTimeZone = value;
        }
    }
    public string EndTimeZone
    {
        get
        {
            return _endTimeZone;
        }
        set
        {
            _endTimeZone = value;
        }
    }
}

{% endhighlight %}

## Binding Remote Data Service

The appointment data can be bound to the Scheduler through [Odata](http://www.odata.org) remote services, by configuring the service URL to the Schedule dataSource through `DataManager`.

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" Width="100%" Height="525px" timeZone="UTC -05:00" AllowDragDrop="false" EnableAppointmentResize="false" CurrentDate="5/6/2014" ReadOnly="true" Create="onCreate">
    <AppointmentSettings Id="Id" Subject="Subject" StartTime="StartTime" EndTime="EndTime" Description="Description" AllDay="AllDay" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
    <DataManager CrossDomain="true" URL="http://mvc.syncfusion.com/OdataServices/Northwnd.svc/Events"/>
</ej:Schedule>

{% endhighlight %}

## OData V4

The OData v4 is an improved version of OData protocols. Scheduler supports retrieving and consuming appointment data from [OData v4](http://www.odata.org/documentation) services, just similar to the other remote services.  

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" Width="100%" Height="525px" CurrentDate="2/23/1997" ReadOnly="true">
    <DataManager CrossDomain="true" URL="http://services.odata.org/V4/Northwind/Northwind.svc/Orders" Adaptor="ODataV4Adaptor" />
    <AppointmentSettings Subject="ShipName" StartTime="OrderDate" EndTime="RequiredDate" Description="ShipAddress"/>
</ej:Schedule>

{% endhighlight %}

## WebAPI Binding

The Schedule appointment data can also be bound through the Web API services. It is a programmatic interface to define the request and response messages system that is mostly exposed in **JSON** or **XML**.

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" Width="100%" Height="525px" CurrentDate="2/23/1997" ReadOnly="true">
    <DataManager CrossDomain="true" URL="http://mvc.syncfusion.com/OdataServices/api/ScheduleData/" Adaptor="WebApiAdaptor" />
    <AppointmentSettings Id="Id" Subject="Subject" StartTime="StartTime" EndTime="EndTime" Description="Description" AllDay="AllDay" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

{% endhighlight %}

The server-side code to retrieve the appointments are as follows.

{% highlight c# %}

    // To retrieve the appointments from database and bind it to Scheduler
    public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
    {
        return new NORTHWNDEntities().Events.ToList();
    }

{% endhighlight %}

## Data Binding using OLEDB

The appointment data can also be bound to the Scheduler using OLEDB database as depicted below.

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <DataManager URL="Schedule.aspx/GetData" CrudURL="Schedule.aspx/CrudResult" InsertURL="Schedule.aspx/InsertData" UpdateURL="Schedule.aspx/UpdateData" RemoveURL="Schedule.aspx/RemoveData" Adaptor="UrlAdaptor"  />
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" StartTimeZone="StartTimeZone" EndTimeZone="EndTimeZone"/>
</ej:Schedule>

{% endhighlight %}

The server-side code to retrieve and bind the appointment data to Scheduler are as follows. Also, define a class with all the required appointment fields as depicted in the below code example.

{% highlight c# %}

        // Define a class with all appointment fields
        public class ScheduleData
        {
            public int Id { get; set; }
            public string Subject { get; set; }
            public DateTime StartTime { get; set; }
            public DateTime EndTime { get; set; }
            public Boolean AllDay { get; set; }
            public Boolean Recurrence { get; set; }
            public string RecurrenceRule { get; set; }
            public string StartTimeZone { get; set; }
            public string EndTimeZone { get; set; }
            public string Description { get; set; }
        }

        // To retrieve the appointments from database and bind it to Scheduler
        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static List<ScheduleData> GetData()
        {
            string strAccessConn = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB";
            OleDbConnection myAccessConn = new OleDbConnection(strAccessConn);
            OleDbCommand myAccessCommand = new OleDbCommand("SELECT * FROM DefaultSchedule", myAccessConn);
            OleDbDataAdapter myDataAdapter = new OleDbDataAdapter(myAccessCommand);
            DataSet myDataSet = new DataSet();            
            myAccessConn.Open();
            myDataAdapter.Fill(myDataSet, "DefaultSchedule");
            List<ScheduleData> datasource = new List<ScheduleData>();
            datasource = myDataSet.Tables[0].AsEnumerable().Select(dataRow => new ScheduleData { Id = dataRow.Field<int>("Id"), Subject = dataRow.Field<string>("Subject"), StartTime = dataRow.Field<DateTime>("StartTime"), EndTime = dataRow.Field<DateTime>("EndTime"), AllDay = dataRow.Field<bool>("AllDay"), Recurrence = dataRow.Field<bool>("Recurrence"), RecurrenceRule = dataRow.Field<string>("RecurrenceRule"), Description = dataRow.Field<string>("Description"), StartTimeZone = dataRow.Field<string>("StartTimeZone"), EndTimeZone = dataRow.Field<string>("EndTimeZone") }).ToList();
            myAccessConn.Close();
            return datasource;
        }

{% endhighlight %}

The server-side code to handle the CRUD operation are as follows.

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static List<ScheduleData> InsertData(ScheduleData value)
        {
            using (OleDbConnection myCon = new OleDbConnection("Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB"))
            {
                OleDbCommand cmd = new OleDbCommand();
                cmd.CommandType = CommandType.Text;
                cmd.CommandText = "INSERT INTO DefaultSchedule(Subject,StartTime,EndTime,AllDay,Recurrence,RecurrenceRule,Description,StartTimeZone,EndTimeZone) VALUES (@Subject,@StartTime,@EndTime,@AllDay,@Recurrence,@RecurrenceRule,@Description,@StartTimeZone,@EndTimeZone)";
                if (string.IsNullOrEmpty(value.Subject))
                    cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@Subject", value.Subject);
                cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
                cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
                cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
                cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
                if (string.IsNullOrEmpty(value.RecurrenceRule))
                    cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
                if (string.IsNullOrEmpty(value.Description))
                    cmd.Parameters.AddWithValue("@Description", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@Description", value.Description);
                if (string.IsNullOrEmpty(value.StartTimeZone))
                    cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
                if (string.IsNullOrEmpty(value.EndTimeZone))
                    cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
                cmd.Connection = myCon;
                myCon.Open();
                cmd.ExecuteNonQuery();
                myCon.Close();
            }
            return GetData();
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static List<ScheduleData> UpdateData(ScheduleData value)
        {
            using (OleDbConnection myCon = new OleDbConnection("Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB"))
            {
                OleDbCommand cmd = new OleDbCommand("UPDATE DefaultSchedule SET Subject=@Subject,StartTime=@StartTime,EndTime=@EndTime,AllDay=@AllDay,Recurrence=@Recurrence,RecurrenceRule=@RecurrenceRule,Description=@Description,StartTimeZone=@StartTimeZone,EndTimeZone=@EndTimeZone  WHERE Id = @Key", myCon);
                if (string.IsNullOrEmpty(value.Subject))
                    cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@Subject", value.Subject);
                cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
                cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
                cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
                cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
                if (string.IsNullOrEmpty(value.RecurrenceRule))
                    cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
                if (string.IsNullOrEmpty(value.Description))
                    cmd.Parameters.AddWithValue("@Description", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@Description", value.Description);
                if (string.IsNullOrEmpty(value.StartTimeZone))
                    cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
                if (string.IsNullOrEmpty(value.EndTimeZone))
                    cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
                else
                    cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
                cmd.Parameters.AddWithValue("@Key", value.Id);
                myCon.Open();
                cmd.ExecuteNonQuery();
                myCon.Close();
            }
            return GetData();
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static List<ScheduleData> RemoveData(int key)
        {
            using (OleDbConnection myCon = new OleDbConnection("Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB"))
            {
                OleDbCommand cmd = new OleDbCommand("DELETE FROM DefaultSchedule WHERE Id = @Key", myCon);
                cmd.Parameters.AddWithValue("@Key", key);
                myCon.Open();
                cmd.ExecuteNonQuery();
                myCon.Close();
            }
            return GetData();
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static List<ScheduleData> CrudResult(List<ScheduleData> added, List<ScheduleData> changed, List<ScheduleData> deleted)
        {
            // Mention your own dataSource to be used here.
            string strAccessConn = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB";
            if (added != null && added.Count > 0)  // this block of code will execute while inserting the appointments
            {
                var value = added[0];
                using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
                {
                    OleDbCommand cmd = new OleDbCommand();
                    cmd.CommandType = CommandType.Text;
                    cmd.CommandText = "INSERT INTO DefaultSchedule(Subject,StartTime,EndTime,AllDay,Recurrence,RecurrenceRule,Description,StartTimeZone,EndTimeZone) VALUES (@Subject,@StartTime,@EndTime,@AllDay,@Recurrence,@RecurrenceRule,@Description,@StartTimeZone,@EndTimeZone)";
                    if (string.IsNullOrEmpty(value.Subject))
                        cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@Subject", value.Subject);
                    cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
                    cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
                    cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
                    cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
                    if (string.IsNullOrEmpty(value.RecurrenceRule))
                        cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
                    if (string.IsNullOrEmpty(value.Description))
                        cmd.Parameters.AddWithValue("@Description", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@Description", value.Description);
                    if (string.IsNullOrEmpty(value.StartTimeZone))
                        cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
                    if (string.IsNullOrEmpty(value.EndTimeZone))
                        cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
                    cmd.Connection = myCon;
                    myCon.Open();
                    cmd.ExecuteNonQuery();
                    myCon.Close();
                }
            }
            if (deleted != null && deleted.Count > 0)  // this block of code will execute while removing the appointment
            {
                foreach (var apps in deleted)
                {
                    using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
                    {
                        OleDbCommand cmd = new OleDbCommand("DELETE FROM DefaultSchedule WHERE Id = @Key", myCon);
                        cmd.Parameters.AddWithValue("@Key", apps.Id);
                        myCon.Open();
                        cmd.ExecuteNonQuery();
                        myCon.Close();
                    }
                }
            }
            if (changed != null && changed.Count > 0)// this block of code will execute while updating the appointment
            {
                var value = changed[0];
                using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
                {
                    OleDbCommand cmd = new OleDbCommand("UPDATE DefaultSchedule SET Subject=@Subject,StartTime=@StartTime,EndTime=@EndTime,AllDay=@AllDay,Recurrence=@Recurrence,RecurrenceRule=@RecurrenceRule,Description=@Description,StartTimeZone=@StartTimeZone,EndTimeZone=@EndTimeZone  WHERE Id = @Key", myCon);
                    if (string.IsNullOrEmpty(value.Subject))
                        cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@Subject", value.Subject);
                    cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
                    cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
                    cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
                    cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
                    if (string.IsNullOrEmpty(value.RecurrenceRule))
                        cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
                    if (string.IsNullOrEmpty(value.Description))
                        cmd.Parameters.AddWithValue("@Description", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@Description", value.Description);
                    if (string.IsNullOrEmpty(value.StartTimeZone))
                        cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
                    if (string.IsNullOrEmpty(value.EndTimeZone))
                        cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
                    else
                        cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
                    cmd.Parameters.AddWithValue("@Key", value.Id);
                    myCon.Open();
                    cmd.ExecuteNonQuery();
                    myCon.Close();
                }
            }
            return GetData();
        }

{% endhighlight %}

## Web Method Binding with CRUD operation

The Scheduler appointment data can retrieve data from code behind Web methods using web services.

{% highlight html %}

<ej:Schedule ID="Schedule1" runat="server" CurrentDate="2015/06/14" OnServerAppointmentSaved="Schedule1_ServerAppointmentSaved" OnServerAppointmentEdited="Schedule1_ServerAppointmentEdited" OnServerAppointmentDeleted="Schedule1_ServerAppointmentDeleted" OnServerResizeStop="Schedule1_ServerResizeStop" OnServerDragStop="Schedule1_ServerDragStop">      
        <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description"/>   <%--Here we are mapping the table fields to the schedule--%>        
</ej:Schedule>

{% endhighlight %}

The server-side code to handle the CRUD operations are as follows.

{% highlight c# %}

namespace ScheduleCRUDWithWebServices
{
    public partial class _Default : Page
    {
        localhost.WebService1 service = new localhost.WebService1();   // Creating the object to the service to call the method
        private string descriptionValue = null;

        protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack) {
                BindAppointments();
            }
        }

        private void BindAppointments()
        {
            DataTable appointmentsData = default(DataTable);
            appointmentsData = service.BindAppointments();
            // Here we are calling the BindAppointments webservice method to read the data
            Schedule1.AppointmentSettings.DataSource = appointmentsData;
            //Here you need to pass the appointment value
        }

        private Dictionary<string, object> m_Arguments;
        public Dictionary<string, object> Arguments
        {
            get { return m_Arguments; }
            set { m_Arguments = value; }
        }

        protected void Schedule1_ServerAppointmentSaved(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
            descriptionValue = list.ContainsKey("Description") == false ? "" : list["Description"].ToString();
            service.Insert(list["Id"], list["Subject"].ToString(), descriptionValue.ToString(), Convert.ToDateTime(list["StartTime"]).ToUniversalTime().ToString(), Convert.ToDateTime(list["EndTime"]).ToUniversalTime().ToString(), Convert.ToBoolean(list["AllDay"])); // Here we are calling the insert Web Service method 
            BindAppointments();
        }

        protected void Schedule1_ServerAppointmentEdited(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
            descriptionValue = list.ContainsKey("Description") == false ? "" : list["Description"].ToString();
            service.Update(list["Id"], list["Subject"].ToString(), descriptionValue.ToString(), Convert.ToDateTime(list["StartTime"]).ToUniversalTime().ToString(), Convert.ToDateTime(list["EndTime"]).ToUniversalTime().ToString(), Convert.ToBoolean(list["AllDay"])); // Here we are calling the update Web Service method 
            BindAppointments();
        }

        protected void Schedule1_ServerAppointmentDeleted(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            var Arguments1 = (System.Collections.ArrayList)e.Arguments["appointment"];
            var list = (Dictionary<String, Object>)Arguments1[0];
            service.Delete(Convert.ToInt32(list["Id"])); // Here we are calling the delete Web Service method 
            BindAppointments();
        }

        protected void Schedule1_ServerResizeStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
            descriptionValue = list.ContainsKey("Description") == false ? "" : list["Description"].ToString();
            service.Update(list["Id"], list["Subject"].ToString(), descriptionValue.ToString(), Convert.ToDateTime(list["StartTime"]).ToUniversalTime().ToString(), Convert.ToDateTime(list["EndTime"]).ToUniversalTime().ToString(), Convert.ToBoolean(list["AllDay"])); // Here we are calling the update Web Service method 
            BindAppointments();
        }

        protected void Schedule1_ServerDragStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
            descriptionValue = list.ContainsKey("Description") == false ? "" : list["Description"].ToString();
            service.Update(list["Id"], list["Subject"].ToString(), descriptionValue.ToString(), Convert.ToDateTime(list["StartTime"]).ToUniversalTime().ToString(), Convert.ToDateTime(list["EndTime"]).ToUniversalTime().ToString(), Convert.ToBoolean(list["AllDay"]));  // Here we are calling the update Web Service method 
            BindAppointments();
        }

    }
}

{% endhighlight %}

The web service  code to handle the CRUD operations are as follows.

{% highlight c# %}

namespace ScheduleCRUDWithWebServices
{
    /// <summary>
    /// Summary description for WebService1
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [System.ComponentModel.ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line. 
    // [System.Web.Script.Services.ScriptService]
    public class WebService1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // The following code snippet is used to get/read the appointment details from the database
        [WebMethod]
        public DataTable BindAppointments()
        {
            string connectionString = ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString;
            SqlConnection conn = new SqlConnection(connectionString);
            SqlDataAdapter adapter1 = new SqlDataAdapter();
            DataSet drugs = new DataSet();
            conn.Open();
            SqlCommand command = new SqlCommand("Select EndTime,Id,StartTime,Subject,AllDay,Description From Appointments", conn);
            // set up the command
            adapter1.SelectCommand = command;
            adapter1.Fill(drugs);
            return drugs.Tables[0];
        }

        // The following code snippet is used to insert the appointment details into the database
        [WebMethod]
        public void Insert(int id, string subject, string description, string startTime, string endTime, bool allDay)
        {
            string connectionString = ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString;
            using (SqlConnection con = new SqlConnection(connectionString))
            {
                using (SqlCommand cmd = new SqlCommand("INSERT INTO Appointments (Id, Subject, Description, StartTime, EndTime, AllDay) VALUES (@Id, @Subject, @Description, @StartTime, @EndTime, @AllDay)"))
                {
                    cmd.Parameters.AddWithValue("@Id", id+1);
                    cmd.Parameters.AddWithValue("@Subject", subject);
                    cmd.Parameters.AddWithValue("@Description", description);
                    cmd.Parameters.AddWithValue("@StartTime", Convert.ToDateTime(startTime));
                    cmd.Parameters.AddWithValue("@EndTime", Convert.ToDateTime(endTime));
                    cmd.Parameters.AddWithValue("@AllDay", allDay);
                    cmd.Connection = con;
                    con.Open();
                    cmd.ExecuteNonQuery();
                    con.Close();
                }
            }
        }
        
        // The following code snippet is used to update the appointment details into the database
        [WebMethod]
        public void Update(int id, string subject, string description, string startTime, string endTime, bool allDay)
        {
            string connectionString = ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString;
            using (SqlConnection con = new SqlConnection(connectionString))
            {
                using (SqlCommand cmd = new SqlCommand("UPDATE Appointments SET Id = @Id, Subject = @Subject, Description=@Description, StartTime=@StartTime, EndTime=@EndTime, AllDay=@AllDay WHERE Id = @Id"))
                {
                    cmd.Parameters.AddWithValue("@Id", id);
                    cmd.Parameters.AddWithValue("@Subject", subject);
                    cmd.Parameters.AddWithValue("@Description", description);
                    cmd.Parameters.AddWithValue("@StartTime", Convert.ToDateTime(startTime));
                    cmd.Parameters.AddWithValue("@EndTime", Convert.ToDateTime(endTime));
                    cmd.Parameters.AddWithValue("@AllDay", allDay);
                    cmd.Connection = con;
                    con.Open();
                    cmd.ExecuteNonQuery();
                    con.Close();
                }
            }
        }

        // The following code snippet is used to update the appointment details into the database
        [WebMethod]
        public void Delete(int id)
        {
            string connectionString = ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString;
            using (SqlConnection con = new SqlConnection(connectionString))
            {
                using (SqlCommand cmd = new SqlCommand("DELETE FROM Appointments WHERE Id = @Id"))
                {
                    cmd.Parameters.AddWithValue("@Id", id);
                    cmd.Connection = con;
                    con.Open();
                    cmd.ExecuteNonQuery();
                    con.Close();
                }
            }
        }


    }
}

{% endhighlight %}

## Loading Data on Demand

Load on demand feature allows the Scheduler to retrieve only the filtered appointment data (for the current Scheduler date range) from the service/database during **loading time**, and that too only for the current Scheduler view. There are 3 parameters made available on the server-side namely **CurrentDate**, **CurrentView** and **CurrentAction** through which only the necessary appointments are retrieved from the database and then assigned to the Scheduler dataSource. With this kind of Scheduler action, consuming only lesser data will reduce the usage of network bandwidth size and loading time. 

The **enableLoadOnDemand** property is used to enable or disable the load on demand functionality of the schedule.

{% highlight html %}

<!-- HTML element will initialize as a ejSchedule -->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" Width="100%" Height="525px" Views="Day,Week,WorkWeek,Month" EnableLoadOnDemand="true" EnableAppointmentNavigation="false" CurrentDate="5/2/2014">
    <DataManager CrudURL="LoadOnDemand.aspx/CrudResult" InsertURL="LoadOnDemand.aspx/InsertData" UpdateURL="LoadOnDemand.aspx/UpdateData" RemoveURL="LoadOnDemand.aspx/RemoveData" URL="LoadOnDemand.aspx/Data" Adaptor="UrlAdaptor"  />
    <AppointmentSettings Id="ID" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" StartTimeZone="StartTimeZone" EndTimeZone="EndTimeZone"/>
</ej:Schedule>

{% endhighlight %}

The server-side code to handle the load on demand is as follows.

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class LoadOnDemand : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            HttpContext.Current.Session["Appointments"] = null;
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object Data(String CurrentView, String CurrentAction, DateTime CurrentDate)
        {
            var data = FilterAppointment(CurrentDate, CurrentAction, CurrentView);
            BatchDataResult result = new BatchDataResult();
            result.result = data;
            result.count = GetAllRecords().ToList().Count > 0 ? GetAllRecords().ToList().Max(p => p.ID) : 1;
            return result;
        }
        public class BatchDataResult
        {
            public IEnumerable result { get; set; }
            public int count { get; set; }
        }
        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static void InsertData(object value)
        {
            ScheduleAppointmentsObjData appointValue = GetObjectValue(value as Dictionary<string, object>);
            GetAllRecords().Insert(0, appointValue);
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static void UpdateData(object value)
        {
            ScheduleAppointmentsObjData obj = GetObjectValue(value as Dictionary<string, object>);
            var filterData = GetAllRecords().ToList().Where(c => c.ID == Convert.ToInt32(obj.ID));
            if (filterData.Count() > 0)
            {
                ScheduleAppointmentsObjData appoint = GetAllRecords().Single(A => A.ID == Convert.ToInt32(obj.ID));
                appoint.StartTime = obj.StartTime;
                appoint.EndTime = obj.EndTime;
                appoint.Subject = obj.Subject;
                appoint.StartTimeZone = obj.StartTimeZone;
                appoint.EndTimeZone = obj.EndTimeZone;
                appoint.Recurrence = obj.Recurrence;
                appoint.AllDay = obj.AllDay;
                appoint.RecurrenceRule = obj.RecurrenceRule;
            }
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static void RemoveData(int key)
        {
            ScheduleAppointmentsObjData removeApp = GetAllRecords().Where(c => c.ID == key).FirstOrDefault();
            if (removeApp != null)
                GetAllRecords().Remove(removeApp);
        }

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static void CrudResult(List<object> added, List<object> changed, List<object> deleted)
        {
            if (added != null && added.Count > 0)
            {
                ScheduleAppointmentsObjData appointValue = GetObjectValue(added[0] as Dictionary<string, object>);
                GetAllRecords().Insert(0, appointValue);
            }
            if (changed != null && changed.Count > 0)
            {
                ScheduleAppointmentsObjData value = GetObjectValue(changed[0] as Dictionary<string, object>);
                var filterData = GetAllRecords().ToList().Where(c => c.ID == Convert.ToInt32(value.ID));
                if (filterData.Count() > 0)
                {
                    ScheduleAppointmentsObjData appoint = GetAllRecords().Where(A => A.ID == Convert.ToInt32(value.ID)).FirstOrDefault();
                    appoint.StartTime = value.StartTime;
                    appoint.EndTime = value.EndTime;
                    appoint.Subject = value.Subject;
                    appoint.StartTimeZone = value.StartTimeZone;
                    appoint.EndTimeZone = value.EndTimeZone;
                    appoint.Recurrence = value.Recurrence;
                    appoint.AllDay = value.AllDay;
                    appoint.RecurrenceRule = value.RecurrenceRule;
                }
            }
            if (deleted != null && deleted.Count > 0)
            {
                foreach (var scheduleDelete in deleted)
                {
                    ScheduleAppointmentsObjData value = GetObjectValue(scheduleDelete as Dictionary<string, object>);
                    ScheduleAppointmentsObjData removeApp = GetAllRecords().Where(c => c.ID == value.ID).FirstOrDefault();
                    if (removeApp != null)
                        GetAllRecords().Remove(removeApp);
                }
            }
        }

        public static ScheduleAppointmentsObjData GetObjectValue(Dictionary<string, object> objValue)
        {
            Dictionary<string, object> KeyVal = objValue;
            ScheduleAppointmentsObjData appointValue = new ScheduleAppointmentsObjData();

            foreach (KeyValuePair<string, object> keyValue in KeyVal)
            {
                if (keyValue.Key == "ID")
                    appointValue.ID = Convert.ToInt32(keyValue.Value);
                else if (keyValue.Key == "Subject")
                    appointValue.Subject = Convert.ToString(keyValue.Value);
                else if (keyValue.Key == "Location")
                    appointValue.Location = Convert.ToString(keyValue.Value);
                else if (keyValue.Key == "StartTime")
                    appointValue.StartTime = Convert.ToDateTime(keyValue.Value).ToString("MM'/'dd'/'yyyy hh:mm:ss tt");
                else if (keyValue.Key == "EndTime")
                    appointValue.EndTime = Convert.ToDateTime(keyValue.Value).ToString("MM'/'dd'/'yyyy hh:mm:ss tt");
                else if (keyValue.Key == "Description")
                    appointValue.Description = Convert.ToString(keyValue.Value);
                else if (keyValue.Key == "AllDay")
                    appointValue.AllDay = Convert.ToBoolean(keyValue.Value);
                else if (keyValue.Key == "Recurrence")
                    appointValue.Recurrence = Convert.ToBoolean(keyValue.Value);
                else if (keyValue.Key == "RecurrenceRule")
                    appointValue.RecurrenceRule = Convert.ToString(keyValue.Value);
                else if (keyValue.Key == "StartTimeZone")
                    appointValue.StartTimeZone = Convert.ToString(keyValue.Value);
                else if (keyValue.Key == "EndTimeZone")
                    appointValue.EndTimeZone = Convert.ToString(keyValue.Value);
            }
            return appointValue;
        }

        public static IList<ScheduleAppointmentsObjData> GetAllRecords()
        {
            IList<ScheduleAppointmentsObjData> appoint = (IList<ScheduleAppointmentsObjData>)HttpContext.Current.Session["Appointments"];
            ScheduleAppointmentsObjDatum obj = new ScheduleAppointmentsObjDatum();
            if (appoint == null)
                HttpContext.Current.Session["Appointments"] = appoint = obj.GetRecords().ToList();
            return appoint;
        }

        public static List<ScheduleAppointmentsObjData> FilterAppointment(DateTime CurrentDate, String CurrentAction, String CurrentView)
        {
            DateTime CurrDate = Convert.ToDateTime(CurrentDate);
            DateTime StartDate = FirstWeekDate(CurrDate.Date);
            DateTime EndDate = FirstWeekDate(CurrDate.Date);
            List<ScheduleAppointmentsObjData> appointmentList = GetAllRecords().ToList();
            switch (CurrentView)
            {
                case "day":
                    StartDate = CurrentDate;
                    EndDate = CurrentDate;
                    break;
                case "week":
                    EndDate = EndDate.AddDays(7);
                    break;
                case "workweek":
                    EndDate = EndDate.AddDays(5);
                    break;
                case "month":
                    StartDate = CurrDate.Date.AddDays(-CurrDate.Day + 1);
                    EndDate = StartDate.AddMonths(1);
                    break;
            }
            appointmentList = GetAllRecords().ToList().Where(app =>
                ((DateTime.ParseExact(app.StartTime.ToString(), "MM/dd/yyyy hh:mm:ss tt", CultureInfo.InvariantCulture).ToLocalTime().Date >= Convert.ToDateTime(StartDate.Date)) &&
                (DateTime.ParseExact(app.StartTime.ToString(), "MM/dd/yyyy hh:mm:ss tt", CultureInfo.InvariantCulture).ToLocalTime().Date <= Convert.ToDateTime(EndDate.Date)) || app.Recurrence == true)).ToList();
            return appointmentList;
        }

        internal static DateTime FirstWeekDate(DateTime CurrentDate)
        {
            try
            {
                DateTime FirstDayOfWeek = CurrentDate;
                DayOfWeek WeekDay = FirstDayOfWeek.DayOfWeek;
                switch (WeekDay)
                {
                    case DayOfWeek.Sunday:
                        break;
                    case DayOfWeek.Monday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-1);
                        break;
                    case DayOfWeek.Tuesday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-2);
                        break;
                    case DayOfWeek.Wednesday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-3);
                        break;
                    case DayOfWeek.Thursday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-4);
                        break;
                    case DayOfWeek.Friday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-5);
                        break;
                    case DayOfWeek.Saturday:
                        FirstDayOfWeek = FirstDayOfWeek.AddDays(-6);
                        break;
                }
                return (FirstDayOfWeek);
            }
            catch
            {
                return DateTime.Now;
            }
        }
       
    }
}

{% endhighlight %}

## XML Data Binding

Scheduler supports binding events data from the XML configured file through XML DataSource which can be referred from the below code example.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="XmlDataSource1" CurrentView="Month" CurrentDate="5/2/2014" Width="100%" Height="525px">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:XmlDataSource ID="XmlDataSource1" runat="server" DataFile="~/App_Data/schedule.xml"></asp:XmlDataSource>

{% endhighlight %}

{% highlight xml %}

<?xml version="1.0" encoding="utf-8" ?>
 <SCHEDULE>
   <APPOINTMENT 
   Id ="100"
   Subject="Bering Sea Gold"
   Location="chennai"
   StartTime="5/2/2014 9:00:00 AM"
   EndTime="5/2/2014 10:30:00 AM"
   Description=""
   Owner="1"
   Priority=""
   Recurrence="0"
   RecurrenceType=""
   RecurrenceTypeCount=""
   RemainderCategorize=""
   CustomStyle=""
   RecurrenceStartDate=""
   RecurrenceEndDate=""
   RecurrenceRule=""
  />
   <APPOINTMENT 
   Id ="101"
   Subject="Bering Sea Gold"
   Location="mum"
   StartTime="5/2/2014 4:00:00 AM"
   EndTime="5/2/2014 5:00:00 AM"
   Description=""
   Owner="1"
   Priority=""
   Recurrence="0"
   RecurrenceType=""
   RecurrenceTypeCount=""
   RemainderCategorize=""
   CustomStyle=""
   RecurrenceStartDate=""
   RecurrenceEndDate=""
   RecurrenceRule=""
  />
   <APPOINTMENT 
   Id ="102"
   Subject="Bering Sea Gold"
   Location="tiruchirapalli"
   StartTime="5/2/2014 4:00:00 PM"
   EndTime="5/2/2014 5:30:00 PM"
   Description=""
   Owner="1"
   Priority=""
   Recurrence="0"
   RecurrenceType=""
   RecurrenceTypeCount=""
   RemainderCategorize=""
   CustomStyle=""
   RecurrenceStartDate=""
   RecurrenceEndDate=""
   RecurrenceRule=""
  /> 
</SCHEDULE>

{% endhighlight %}


## Binding Data through LINQ to SQL

Scheduler supports binding events data through LINQ-to-SQL, which can be referred from the below code example.

{% highlight html %}

<ej:Schedule ID="Schedule1" runat="server" Height="525px" CurrentDate="6/8/2015" OnServerAppointmentSaved="Schedule1_ServerAppointmentSaved" OnServerAppointmentEdited="Schedule1_ServerAppointmentEdited" OnServerAppointmentDeleted="Schedule1_ServerAppointmentDeleted" OnServerDragStop="Schedule1_ServerDragStop" OnServerResizeStop="Schedule1_ServerResizeStop">
<AppointmentSettings Id="Id" Subject="Subject" Description="Description" StartTime="StartTime" EndTime="EndTime" AllDay="AllDay"  Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>  

{% endhighlight %}

The code to handle the CRUD operation of the appointments at code behind can be referred from the below example,

{% highlight c# %}

    public partial class _Default : Page
    {
        ScheduleDataDataContext db = new ScheduleDataDataContext();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
           
        protected void Page_Load(object sender, EventArgs e)
        {
            Schedule1.AppointmentSettings.DataSource = db.GetTable<ScheduleAppointment>().ToList();
            Schedule1.DataBind();
        }
        //The following block of codes used to display the appointments after the add/edit/delete the appointments
        private void BindAppointments()
        {
            Schedule1.AppointmentSettings.DataSource = db.GetTable<ScheduleAppointment>().ToList();
            Schedule1.DataBind();
        }
           
        //The following block of codes will trigger and perform the storing appointments details after the add/saving the appointments
        protected void Schedule1_ServerAppointmentSaved(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
           
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string,object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if(property!= null && item.Value !=null)
                {
                    if (item.Key == "StartTime" || item.Key =="EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            int intMax = db.ScheduleAppointments.ToList().Count > 0 ? db.ScheduleAppointments.ToList().Max(p => p.Id) : 1;

            ScheduleAppointment appoint = new ScheduleAppointment()
            {
                Id= intMax + 1,
                Subject=Appoint.Subject,
                Description=Appoint.Description,
                StartTime=Appoint.StartTime,
                EndTime=Appoint.EndTime ,
                AllDay=Appoint.AllDay,
                Recurrence=Appoint.Recurrence,
                RecurrenceRule=Appoint.RecurrenceRule
            };
            db.ScheduleAppointments.InsertOnSubmit(appoint);
            db.SubmitChanges();
            BindAppointments();
        }
        
       //The following block of codes will trigger and perform the storing appointments details after the editing/modify the appointments
        protected void Schedule1_ServerAppointmentEdited(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            int intMax = db.ScheduleAppointments.ToList().Count > 0 ? db.ScheduleAppointments.ToList().Max(p => p.Id) : 1;

            ScheduleAppointment appoint = new ScheduleAppointment()
            {
                Id = intMax + 1,
                Subject = Appoint.Subject,
                Description = Appoint.Description,
                StartTime = Appoint.StartTime,
                EndTime = Appoint.EndTime,
                AllDay = Appoint.AllDay,
                Recurrence = Appoint.Recurrence,
                RecurrenceRule = Appoint.RecurrenceRule
            };
            db.ScheduleAppointments.InsertOnSubmit(appoint);
            db.SubmitChanges();
            BindAppointments();
        }
        //The following block of codes will trigger and perform the deleting appointments details after deleting the appointment
        protected void Schedule1_ServerAppointmentDeleted(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (IEnumerable items in div)
            {
               
            foreach (KeyValuePair<string, object> item in items)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            }
           var app = db.ScheduleAppointments.Where(a => a.Id == Appoint.Id).FirstOrDefault();
           if (app != null) db.ScheduleAppointments.DeleteOnSubmit(app);
           db.SubmitChanges();
           BindAppointments();
        }     
        
        //The following block of codes will trigger and perform the update appointments details after drag and drop the appointment
        protected void Schedule1_ServerDragStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            var intMax = db.ScheduleAppointments.Where(c => c.Id == Appoint.Id);

            if (intMax.Count() > 0)
                {
                    ScheduleAppointment appoint = db.ScheduleAppointments.Single(a => a.Id == Appoint.Id);
                    appoint.Subject = Appoint.Subject;
                    appoint.Description = Appoint.Description;
                    appoint.StartTime = Appoint.StartTime;
                    appoint.EndTime = Appoint.EndTime;
                    appoint.AllDay = Appoint.AllDay;
                    appoint.Recurrence = Appoint.Recurrence;
                    appoint.RecurrenceRule = Appoint.RecurrenceRule;
            }
            db.SubmitChanges();
           BindAppointments();
        }
        //The following block of codes will trigger and perform the update appointments details after resizing the appointment
        protected void Schedule1_ServerResizeStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            var intMax = db.ScheduleAppointments.Where(c => c.Id == Appoint.Id);

            if (intMax.Count() > 0)
            {
                ScheduleAppointment appoint = db.ScheduleAppointments.Single(a => a.Id == Appoint.Id);
                appoint.Subject = Appoint.Subject;
                appoint.Description = Appoint.Description;
                appoint.StartTime = Appoint.StartTime;
                appoint.EndTime = Appoint.EndTime;
                appoint.AllDay = Appoint.AllDay;
                appoint.Recurrence = Appoint.Recurrence;
                appoint.RecurrenceRule = Appoint.RecurrenceRule;
            }
            db.SubmitChanges();
            BindAppointments();
        }
        
    }
    public class ScheduleFields
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Description { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public bool AllDay { get; set; }
        public bool Recurrence { get; set; }
        public string RecurrenceRule { get; set; }
    }

{% endhighlight %}

## Binding Data with Entity Framework

To bind the Scheduler events data through Entity Framework, refer the below code example.

{% highlight html %}

<ej:Schedule ID="Schedule1" runat="server" Height="525px" TimeZone="+00:00" CurrentDate="6/8/2015" OnServerAppointmentSaved="Schedule1_ServerAppointmentSaved" OnServerAppointmentEdited="Schedule1_ServerAppointmentEdited" OnServerAppointmentDeleted="Schedule1_ServerAppointmentDeleted" OnServerDragStop="Schedule1_ServerDragStop" OnServerResizeStop="Schedule1_ServerResizeStop">
<AppointmentSettings Id="Id" Subject="Subject" Description="Description" StartTime="StartTime" EndTime="EndTime" AllDay="AllDay"  Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule> 

{% endhighlight %}

Create a data entity with necessary database tables and then create a object of its generated classes to access the tables and fields within it.

{% highlight c# %}

namespace ScheduleCRUDCS
{
    public partial class _Default : Page
    {
        ScheduleDataEntities1 db = new ScheduleDataEntities1();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
           
        protected void Page_Load(object sender, EventArgs e)
        {
            Schedule1.AppointmentSettings.DataSource = db.ScheduleAppointments.ToList();
            Schedule1.DataBind();
        }
        //The following block of codes used to display the appointments after the add/edit/delete the appointments
        private void BindAppointments()
        {
            Schedule1.AppointmentSettings.DataSource = db.ScheduleAppointments.ToList();
            Schedule1.DataBind();
        }
           
        //The following block of codes will trigger and perform the storing appointments details after the add/saving the appointments
        protected void Schedule1_ServerAppointmentSaved(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            int intMax = db.ScheduleAppointments.ToList().Count > 0 ? db.ScheduleAppointments.ToList().Max(p => p.Id) : 1;

            ScheduleAppointment appoint = new ScheduleAppointment()
            {
                Id = intMax + 1,
                Subject = Appoint.Subject,
                Description = Appoint.Description,
                StartTime = Appoint.StartTime,
                EndTime = Appoint.EndTime,
                AllDay = Appoint.AllDay,
                Recurrence = Appoint.Recurrence,
                RecurrenceRule = Appoint.RecurrenceRule
            };
            db.ScheduleAppointments.Add(appoint);
            db.SaveChanges();
            BindAppointments();
           
        }
        
       //The following block of codes will trigger and perform the storing appointments details after the editing/modify the appointments
        protected void Schedule1_ServerAppointmentEdited(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            var intMax = db.ScheduleAppointments.Where(c => c.Id == Appoint.Id);

            if (intMax.Count() > 0)
            {
                ScheduleAppointment appoint = db.ScheduleAppointments.Single(a => a.Id == Appoint.Id);
                appoint.Subject = Appoint.Subject;
                appoint.Description = Appoint.Description;
                appoint.StartTime = Appoint.StartTime;
                appoint.EndTime = Appoint.EndTime;
                appoint.AllDay = Appoint.AllDay;
                appoint.Recurrence = Appoint.Recurrence;
                appoint.RecurrenceRule = Appoint.RecurrenceRule;
            }
            db.SaveChanges();
            BindAppointments();
        }
        //The following block of codes will trigger and perform the deleting appointments details after deleting the appointment
        protected void Schedule1_ServerAppointmentDeleted(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (IEnumerable items in div)
            {

                foreach (KeyValuePair<string, object> item in items)
                {
                    var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                    if (property != null && item.Value != null)
                    {
                        if (item.Key == "StartTime" || item.Key == "EndTime")
                        {
                            property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                        }
                        else
                        {
                            Type type = property.PropertyType;
                            string serialize = serializer.Serialize(item.Value);
                            object value1 = serializer.Deserialize(serialize, type);
                            property.SetValue(Appoint, value1, null);
                        }

                    }
                }
            }
            var app = db.ScheduleAppointments.Where(a => a.Id == Appoint.Id).FirstOrDefault();
            if (app != null) db.ScheduleAppointments.Remove(app);
            db.SaveChanges();
            BindAppointments();
        }     
        
        The following block of codes will trigger and perform the update appointments details after drag and drop the appointment
        protected void Schedule1_ServerDragStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            var intMax = db.ScheduleAppointments.Where(c => c.Id == Appoint.Id);

            if (intMax.Count() > 0)
            {
                ScheduleAppointment appoint = db.ScheduleAppointments.Single(a => a.Id == Appoint.Id);
                appoint.Subject = Appoint.Subject;
                appoint.Description = Appoint.Description;
                appoint.StartTime = Appoint.StartTime;
                appoint.EndTime = Appoint.EndTime;
                appoint.AllDay = Appoint.AllDay;
                appoint.Recurrence = Appoint.Recurrence;
                appoint.RecurrenceRule = Appoint.RecurrenceRule;
            }
            db.SaveChanges();
            BindAppointments();
        }
        //The following block of codes will trigger and perform the update appointments details after resizing the appointment
        protected void Schedule1_ServerResizeStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            IEnumerable div = e.Arguments["appointment"] as IEnumerable;

            ScheduleFields Appoint = new ScheduleFields();
            foreach (KeyValuePair<string, object> item in div)
            {
                var property = Appoint.GetType().GetProperty(item.Key, BindingFlags.IgnoreCase | BindingFlags.DeclaredOnly | BindingFlags.Instance | BindingFlags.Public);
                if (property != null && item.Value != null)
                {
                    if (item.Key == "StartTime" || item.Key == "EndTime")
                    {
                        property.SetValue(Appoint, Convert.ToDateTime(item.Value), null);
                    }
                    else
                    {
                        Type type = property.PropertyType;
                        string serialize = serializer.Serialize(item.Value);
                        object value1 = serializer.Deserialize(serialize, type);
                        property.SetValue(Appoint, value1, null);
                    }

                }
            }
            var intMax = db.ScheduleAppointments.Where(c => c.Id == Appoint.Id);

            if (intMax.Count() > 0)
            {
                ScheduleAppointment appoint = db.ScheduleAppointments.Single(a => a.Id == Appoint.Id);
                appoint.Subject = Appoint.Subject;
                appoint.Description = Appoint.Description;
                appoint.StartTime = Appoint.StartTime;
                appoint.EndTime = Appoint.EndTime;
                appoint.AllDay = Appoint.AllDay;
                appoint.Recurrence = Appoint.Recurrence;
                appoint.RecurrenceRule = Appoint.RecurrenceRule;
            }
            db.SaveChanges();
            BindAppointments();

        }
        
    }
    public class ScheduleFields
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Description { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public bool AllDay { get; set; }
        public bool Recurrence { get; set; }
        public string RecurrenceRule { get; set; }
    }
}

{% endhighlight %}