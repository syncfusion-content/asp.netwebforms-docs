---
title: Schedule - Resource handling with multiple option
description: This section explains how to handle multiple resources support on the Syncfusion ASP.NET Web Forms Schedule control.
platform: aspnet
control: schedule
documentation: ug
keywords: resource, resources, multiple resources, grouping 
---
# Resources

The Scheduler provides **Resources** support, with which the single Scheduler is shared by multiple resources simultaneously. Each resource in the Scheduler is arranged in a column/row wise, with individual spacing to display all its respective appointments on a single page. It also supports the grouping of resources, thus enabling the categorization of resources in a hierarchical structure and shows it either in expandable groups (**Horizontal** **view**) or else vertical hierarchy one after the other (**Vertical** **view**).

One or more resources can be assigned to the Scheduler appointments by making selection of the resource options available in the appointment window.

## Fields of Resources

The default options available within the 'Resources' collection are as follows,

### Name (**String**)

A unique resource name which is used for differentiating various resource objects while grouping it in levels.

### Title (**String**)

It holds the title name of the resource field to be displayed on the Scheduler appointment window.

### Field (**String**)

It holds the name of the resource field to be bound to the Scheduler appointments which contains the resource Id.

### AllowMultiple (**Boolean**)

When set to true, allows multiple selection of resource names, thus creating multiple instances of same appointment for the selected resources.

### ResourceSettings (**Object**)

It holds the field names of the resources dataSource to be bound to the Scheduler.

The following are the resource fields which must be defined within the **ResourceSettings** that holds the appropriate column names from the dataSource.

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Text<br/><br/></td><td>
Binds the text field name in the dataSource to the resourceSettings <b>Text</b>. These text gets listed out in the resources field of the appointment window. It’s mandatory.<br/><br/><br/><br/></td></tr>
<tr>
<td>
id<br/><br/></td><td>
Binds the Id field name in the dataSource to the resourceSettings <b>Id</b>. It’s mandatory.<br/><br/><br/><br/></td></tr>
<tr>
<td>
GroupId<br/><br/></td><td>
Binds the GroupId field name in the dataSource to the resourceSettings <b>GroupId</b>. This field is not necessary for a resource object (resource data) defined as first level within the resources collection.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Color<br/><br/></td><td>
Binds the Color field name in the dataSource to the resourceSettings <b>Color</b>. It is optional.<br/><br/><br/><br/></td></tr>
<tr>
<td>
AppointmentClass<br/><br/></td><td>
Binds the AppointmentClass field name in the dataSource. It applies the custom CSS class name to the appointments based on the resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Start<br/><br/></td><td>
Binds the starting work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the starting work hour for specific resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
End<br/><br/></td><td>
Binds the end work hour field name in the dataSource. It's optional, but when provided with some numeric value will set the end work hour for specific resources.<br/><br/><br/><br/></td></tr>
<tr>
<td>
WorkWeek<br/><br/></td><td>
Binds the resources working days field name in the dataSource. It's optional, and accept array of strings which is nothing but only the week day names. When provided with some values (array of day names), only those days will render for the specific resources.<br/><br/><br/><br/></td></tr>
</table>

**Example**: To set the Resources options using all the above specified fields,

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" CurrentView="Workweek">
    <Resources>
        <ej:Resources Field="RoomId" Name="Rooms" Title="Room" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text" Start="workHourStart", End="workHourEnd", WorkWeek="customDays" >
            </ResourceSettings>
        </ej:Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text" GroupId="groupId">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="RoomId,OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class ResourceGrouping : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<WebSampleBrowser.Schedule.multipleResource.Rooms> owner = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            List<WebSampleBrowser.Schedule.multipleResource.Rooms> rooms = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room1", id = "1", color = "#cb6bb2",workHourStart= 10, workHourEnd= 18, customDays= new List<string> {"Monday","Wednesday","Friday"} });
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room2", id = "2", color = "#56ca85",workHourStart= 6, workHourEnd= 10, customDays= new List<string> {"Monday","Saturday"} });

            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Nancy", id = "1", groupId = "1", color = "#ffaa00" });
            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Steven", id = "3", groupId = "2", color = "#f8a398" });
            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Michael", id = "5", groupId = "1", color = "#7499e1" });

            Schedule1.Resources[0].ResourceSettings.DataSource = rooms;
            Schedule1.Resources[1].ResourceSettings.DataSource = owner;
        }
    }
}

{% endhighlight %}

N> The resource object defined at **first level** within the **Resources** collection doesn’t make use of the **GroupId** field, as there is no previous levels applicable to map.

## Data Binding

The resources data can be bound to the Schedule control through the **ResourceSettings** option available within the **Resources** property. The data-binding can be done either using JSON object collection or [DataManager](/aspnet/datamanager/overview)  instance which contains the resources related data.

### Binding List Data Collection

**Example**: To set the resource data with List of resources data collection.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014">
    <Group Resources="Owners"/>
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>
            
{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class multipleResource : System.Web.UI.Page
    {
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
    }
}

{% endhighlight %}

### Remote Data

**Example**: To set the resource data through remote service URL,

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014">
    <Group Resources="Owners"/>
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Text="CategoryName" Id="CategoryID">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class multipleResource : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            Schedule1.Resources[0].ResourceSettings.DataSource = "http://mvc.syncfusion.com/OdataServices/Northwnd.svc/Categories";
        }
    }
}

{% endhighlight %}


## Multiple Resources (Without Grouping)

It is possible to display the Scheduler in default look without visually showcasing all the resources on it, but it allow the user to assign the required resources to the appointments through the appointment window resource options.

The appointments belonging to all the resources will be displayed on the Scheduler which will be differentiated based on the resource color assigned in the **ResourceSettings** (depicting to which resource that particular appointment belongs). 

**Example**: To display default Scheduler with multiple resource options in the appointment window,

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014">
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
</ej:Schedule>

 <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class HorizontalMultipleResource : System.Web.UI.Page
    {
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
    }
}

{% endhighlight %}

N> Setting **AllowMultiple** to **true** in the above code snippet allows the user to select multiple resources in the appointment window and also creates multiple copies of the same appointment in the Scheduler for each resources while saving.

## Grouping

Scheduler supports both single and multiple levels of resource grouping that can be customized either in horizontal or vertical Scheduler views. In Vertical view - the levels are displayed in a tree structure one after the other, but in horizontal view – the levels are grouped in a vertically expandable/collapsible structure.

### Single-Level

This type of grouping allows the Scheduler to display all the resources at a single level simultaneously. The appointments will make use of the **color** defined for the first resource instance as its background color. 

**Example**: To display the Scheduler with single level resource grouping options,

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014">
    <Group Resources="Owners" />
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class HorizontalMultipleResource : System.Web.UI.Page
    {
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
    }
}

{% endhighlight %}

N> The **Name** field mentioned in the **Resource** object needs to be specified within the **Group** property in order to enable the grouping option in Scheduler.

### Multi-Level

This type of grouping displays the resources in the Scheduler at multiple levels with a set of resources grouped under each parent. The appointments will make use of the **color** defined for the first/top level resource instance as its background color.  

**Example**: To display the Scheduler with multiple level resource grouping options,

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" CurrentView="Workweek">
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

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class ResourceGrouping : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<WebSampleBrowser.Schedule.multipleResource.Rooms> owner = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            List<WebSampleBrowser.Schedule.multipleResource.Rooms> rooms = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room1", id = "1", color = "#cb6bb2" });
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room2", id = "2", color = "#56ca85" });

            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Nancy", id = "1", groupId = "1", color = "#ffaa00" });
            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Steven", id = "3", groupId = "2", color = "#f8a398" });
            owner.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Michael", id = "5", groupId = "1", color = "#7499e1" });

            Schedule1.Resources[0].ResourceSettings.DataSource = rooms;
            Schedule1.Resources[1].ResourceSettings.DataSource = owner;
        }
    }
}

{% endhighlight %}

N> Here, the appointments will make use of the **color** defined for the Owners resource instance as its background color.


### Different Working days and Hours for Resources

It is possible to assign different workdays and workhours for each resources present within the Scheduler. The process of assigning different working days for every individual resources is applicable only for the vertical Scheduler mode and not for timeline view, whereas the customization of workhours for each resources is applicable on both the Scheduler orientation. The custom workdays and workhours needs to be defined within the `ResourceSettings` property using the following 3 sub-properties available within it.

* Start – To define the work start hour for each individual resources
* End – To define the work end hour for each individual resources
* WorkWeek – To define the working days for each individual resources

**Example**: To display the Scheduler with each resources having different workhours and workdays, the code example is depicted below.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" CurrentView="Workweek">
    <Resources>
        <ej:Resources Field="RoomId" Name="Rooms" Title="Room" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
            </ResourceSettings>
        </ej:Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text" GroupId="groupId" Start="start" End="end" WorkWeek="workweek">
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <Group Resources="Rooms,Owners"/>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="RoomId,OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>" SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class ResourceGrouping : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<WebSampleBrowser.Schedule.multipleResource.Rooms> rooms = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room1", id = "1", color = "#cb6bb2" });
            rooms.Add(new WebSampleBrowser.Schedule.multipleResource.Rooms { text = "Room2", id = "2", color = "#56ca85" });

            List<WebSampleBrowser.Schedule.multipleResource.Rooms> owner = new List<WebSampleBrowser.Schedule.multipleResource.Rooms>();
            owner.Add(new Owners { text = "Nancy", id = "1", groupId = "1", color = "#ffaa00", start = "10", end = "18", workweek = new List<string> {"Monday","Wednesday","Friday"} });
            owner.Add(new Owners { text = "Steven", id = "3", groupId = "2", color = "#f8a398", start = "6", end = "10", workweek = new List<string> { "Tuesday", "Thursday" } });
            owner.Add(new Owners { text = "Michael", id = "5", groupId = "1", color = "#7499e1", start = "11", end = "15", workweek = new List<string> { "Sunday", "Tuesday", "Thursday", "Saturday" } });

            Schedule1.Resources[0].ResourceSettings.DataSource = rooms;
            Schedule1.Resources[1].ResourceSettings.DataSource = owner;
        }
    }
}

{% endhighlight %}

