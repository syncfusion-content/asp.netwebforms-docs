---
title: Schedule - Template
description: This section explains how to define the templates and its functionalities using the Syncfusion ASP.NET Web Forms Schedule control.
platform: aspnet
control: schedule
documentation: ug
keywords: appointment template, template, cell template, resource header 
---
# Template

Template is applicable to all the below specified elements of the Scheduler,

* Appointments
* Cells
* Date Header
* Resource header
* TimeScale
* Priority field
* Date and time columns in Agenda view
* Tooltip

## Appointment Template

The template design that applies on for the Scheduler appointments. The field names that are mapped from the dataSource to the appropriate field properties within the [appointmentSettings](/js/api/ejschedule#members:appointmentsettings) can be accessed within the template.

Apart from the dataSource field names, the template can also access the current view of the Scheduler using the name **View** – which can contain either of the following values in lowercase. 

* day
* week
* workweek
* agenda
* month
* customview

It is controlled by an API named `AppointmentTemplateId` which accepts the id value of the template design block preceded by a symbol **#**.

Usually, the appointments are displayed with its **Subject** and **Start/End time** on the Scheduler. If suppose, the subject needs to be accompanied with location text, it can be done with the following code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentView="Month" Width="100%" Height="525px" AppointmentTemplateId="#apptemplate" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" Location="Location" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" />
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
     <script id="apptemplate" type="text/x-jsrender">
       {{"{{"}}if View !== "agenda"{{}}}}
        <div style="height:100%; background-color:orange; margin-left: 5px;">
            <div style="margin-left: 2px;">{{"{{"}}:Subject{{}}}}</div>
            <div style="margin-left: 2px;">{{"{{"}}:Location{{}}}}</div>
        </div>
    {{"{{"}}else{{}}}}
        <div>{{"{{"}}:Subject{{}}}}, {{"{{"}}:Location{{}}}}</div>
    {{"{{"}}/if{{}}}}
</script>
</asp:Content>           

{% endhighlight %}

## Cell Templates

The template design that applies on the Scheduler elements such as all-day cells, work cells and month cells which allows the customization to be done based on the date, view, resources and timescale. The cells can be customized to add images, colors, and other elements etc and can also access the current view of the Scheduler using the name **view**.

**All-day cells** - An API named `AllDayCellsTemplateId` can be used to customize the all-day cells, which accepts the id of the template design block preceded with a symbol **#**.

**Work cells and Month cells** - An API named `WorkCellsTemplateId` can be used to customize the work cells in all the views, which accepts the id of the template design block preceded by a symbol **#**. 

The cells can be customized with the following code example.

 {% highlight html %}
 
 <ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" AllDayCellsTemplateId="#alldayTemplate" WorkCellsTemplateId="#workTemplate">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">

    <!-- Template for Alldaycells -->
<script id="alldayTemplate" type="text/x-jsrender">
    <div class="e-icon e-scheduleallday" style="opacity:0.5"></div>
    <span style="opacity:0.5">AllDay</span>
</script>

<!-- Template for Workcells and Monthcells -->
<script id="workTemplate" type="text/x-jsrender">
    {{"{{"}}if resource.classname == 'e-parentnode'{{}}}}
        {{"{{"}}:resource.text {{}}}}
    {{"{{"}}else{{}}}}
        {{"{{"}}if date.getDay() == 0 || date.getDay() == 6{{}}}}
            <div style="background-color:lightblue">Weekend</div>
        {{"{{"}}else{{}}}}
            {{"{{"}}if view == 'month' && resource.text == 'Party Hall-A' && date.getDay() == 5{{}}}}
                <div style="background-color:burlywood">Meeting</div>
            {{"{{"}}else resource.text != 'Party Hall-B' && date.getDate() == 15{{}}}}
                <div style="background-color:thistle">Holiday</div>
            {{"{{"}}else view != 'month' && resource.text == 'Party Hall-A' && date.getDay() == 5 && date.getHours() == 10{{}}}}
                <div style="background-color:burlywood">Meeting</div>
            {{"{{"}}else view == 'month' && resource.text == 'Party Hall-B' && date.getDay() == 5{{}}}}
                <div style="background-color:lightblue">Conf.</div>
            {{"{{"}}else resource.text == 'Party Hall-B' && date.getDate() == 16{{"}}"}
                <div style="background-color:darkkhaki">HappyDay</div>
            {{"{{"}}else view != 'month' && resource.text == 'Party Hall-B' && date.getDay() == 5 && date.getHours() == 12{{}}}}
                <div style="background-color:goldenrod">Conf.</div>
            {{"{{"}}else date.getDate() == 10 && date.getMonth() == 11{{}}}}
                <div style="background-color:palegreen">Day Special</div>
            {{"{{"}}else date.getDate() == 25 && date.getMonth() == 11{{}}}}
                <div style="background-color:sandybrown">Christmas</div>
            {{"{{"}}/if{{}}}}
        {{"{{"}}/if{{}}}}
    {{"{{"}}/if{{}}}}
</script>

</asp:Content>
 
 {% endhighlight %}

## Date Header Template

The template design that applies on for the date header part of the Scheduler. An API named `DateHeaderTemplateId` can be used to customize the date header which accepts the id value of the template design block preceded by a symbol **#**. The template can also access the current view of the Scheduler in using the name **view**.

The Date header can be customized with the following code example.

{% highlight html %}
  
   <ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" DateHeaderTemplateId="#dateTemplate">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
   </ej:Schedule>
   
   <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <!-- Template for Dateheader -->
    <script id="dateTemplate" type="text/x-jsrender">
        <div>{{"{{"}}:~dTemplate(date){{}}}}</div>
    </script>

    <script>
        function _dateFormat(date) {
            var dFormat = ej.format(new Date(date), "dd/MM");
            return dFormat;
        }
        $.views.helpers({ dTemplate: _dateFormat });
    </script>

</asp:Content>
  
{% endhighlight %}

## Resource Header Template

The template structure that applies on the resource headers of the Scheduler. By default, only the resource names will be displayed on the resource header bar. Also, the way of rendering resource headers on the Scheduler is comparatively different for both the vertical and horizontal scheduler views.  

The field names that are mapped from the dataSource to the appropriate field properties within the **ResourceSettings** can be accessed within the resource header template.

### Resource Header Template in Vertical View

To customize the resource header with some additional images or other customizations in **vertical** **Scheduler** **View** – refer the below code example.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" ResourceHeaderTemplateId="#resTemplate"  CurrentDate="5/5/2014">
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
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
<script id="resTemplate" type="text/x-jsrender">
  <div style="height:100%">
        <div style="width:15px;height:15px;margin-left:275px;margin-top:2px;float:left;background:{{"{{"}}:color"}{{}}};"></div><div style="float:left;margin-left:5px;">{{"{{"}}:text"}{{{}}}</div> 
    </div>
</script>
</asp:Content>

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

### Resource Header Template in Horizontal View

To perform the above specified same customization in **horizontal** **Scheduler** **view**, the template structure varies a little bit as depicted below.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" ResourceHeaderTemplateId="#resTemplate" Orientation="Horizontal"  CurrentDate="5/5/2014">
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
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
<script id="resTemplate" type="text/x-jsrender">
   <div style="height:100%">
        <div style="width:15px;height:15px;margin-right:5px;margin-top:2px;float:left;background:{{:color}};"></div><div>{{:text}}</div> 
    </div>
</script>
</asp:Content>           

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

N> In horizontal Scheduler, the header template makes use of an additional field namely **classname** which holds either **e-parentnode** or **e-childnode** value. The field **classname** can be used in the application scenario to check for the parent or child header node. You can apply the different template customization accordingly based on it.

## TimeScale Templates

The `TimeScale` is also availed with template options to allow customization. It includes the following 2 properties for customization -

* `MajorSlotTemplateId` - Accepts the id value of the template design block preceded by a symbol **#**, which gets applied for the major time slots.
* `MinorSlotTemplateId` - Accepts the id value of the template design block preceded by a symbol **#**, which gets applied for the minor time slots.

The template customization for major and minor timeslots can be referred from the following code example.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <TimeScale MajorSlotTemplateId="#majorTemplate" MinorSlotTemplateId="#minorTemplate" />
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
   <!-- Template for Majorslot -->
<script id="majorTemplate" type="text/x-jsrender">
    <div>{{"{{"}}:~major(date){{}}}}</div>
</script>

<!-- Template for Minorslot -->
<script id="minorTemplate" type="text/x-jsrender">
    <div>{{"{{"}}:~minor(date){{}}}}</div>
</script>

<script type="text/javascript">
    function _majorFormat(date) {
        var dFormat = ej.format(new Date(date), "hh:mm:ss");
        return dFormat;
    }
    $.views.helpers({ major: _majorFormat });

    function _minorFormat(date) {
        var dFormat = ej.format(new Date(date), "hh:mm:ss");
        return dFormat;
    }
    $.views.helpers({ minor: _minorFormat });
</script>

</asp:Content>           

{% endhighlight %}

## Priority Settings Template

The template design which can be applied to the content of the priority field in the appointment window. By default, the appropriate icons are displayed for each priority options such as **None**, **High**, **Medium** and **Low**. 

When template is applied for the `PrioritySettings`, these default icons will be replaced by the custom icons or styles defined newly. The following code example depicts the way to enable the priority settings and to define the new custom styles to replace the default icons in the Priority field.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
    <PrioritySettings Enable="true" Text="text" Value="value" Template="<div class='${text}'></div>"></PrioritySettings>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Location="Location" Priority="Priority" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection">
    <style type="text/css">
    .Critical,
	.UltraCritical,
	.None {
		height: 13px;
		width: 13px;
		float: left;
		margin-right: 4px;
		background-repeat: no-repeat;
		background-size: 60px;
		padding: 1px;
		margin-top: 2px;
	}

	.Critical {
		background-color: orange;
		background-position: -13px;
	}

	.UltraCritical {
		background-color: #56ca85;
		background-position: -59px;
	}
        </style>
</asp:Content>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class Default : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Priority> priority = new List<Priority>();
            priority.Add(new Priority { text = "None", value = "none" });
            priority.Add(new Priority { text = "Critical", value = "Critical" });
            priority.Add(new Priority { text = "Ultra Critical", value = "Ultra Critical" });
            Schedule1.PrioritySettings.DataSource = priority;
        }
        public class Priority
        {
            public string text { get; set; }
            public string value { get; set; }
        }
    }
}

{% endhighlight %}

The custom style class names defined for the priority template should be same as that of the values defined for each priority option within the dataSource, so that it applies properly.

N> Additionally, the priority field within the `AppointmentSettings` should be defined with appropriate dataSource field name. When an appointment is assigned with a priority value, the custom style/icon defined for that priority option will get applied over that appointment.

## Tooltip Template

The tooltip can be applied with the customized template design. Currently the tooltip support is provided only for the appointments and the default tooltip displays the Subject and duration on hovering across the appointments. 

By making use of template feature with tooltip, all the field names that are mapped from the dataSource to the appropriate field properties within the **AppointmentSettings** can be accessed.

To define the template option for tooltip, the `TooltipSettings` must be enabled first. The following code example depicts the way to add the tooltip template.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" CurrentDate="5/2/2014">
    <ToolTipSettings Enable="true" TemplateId="#tooltipTemplate" />
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Location="Location" Priority="Priority" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script id="tooltipTemplate" type="text/x-jsrender">
    <div style="width:145px">
        <div style="width:145px">
        <div style="padding-top:3px;">
            <div style="float:left; font:13px Segoe UI; font-weight:bold;">Subject&nbsp;&nbsp;:&nbsp;</div>
            <div style="padding-top:2px; font:12px Segoe UI SemiBold;">{{"{{"}}:Subject{{}}}}</div>
        </div>
        <div style="padding-top:3px">
            <div style="float:left; font:13px Segoe UI; font-weight:bold;">Location:&nbsp;</div>
            <div style="padding-top:2px; font:12px Segoe UI SemiBold;">{{"{{"}}:Location{{}}}}</div>
        </div>
    </div>
</script>
</asp:Content>

{% endhighlight %}

## Agenda View Templates

Agenda View provides two separate templates – one for date column and another for time column. These templates allows the customization of the content of both the date and time columns. Apart from this, the event column can also be customized through the existing API named `AppointmentTemplateId`.

The following code snippet shows how to customize the content of the date, time and event column.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" AppointmentTemplateId="#apptemplate" CurrentDate="5/2/2014">
    <AgendaViewSettings DateColumnTemplateId="#datetemplate" TimeColumnTemplateId="#timetemplate" />
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Location="Location" Priority="Priority" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
            
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
  // Template for date column
<script id="datetemplate" type="text/x-jsrender">
    <div style="height:100%">
        <div>
            <div>{{"{{"}}:~dateDisplay(StartTime){{}}}}</div>
        </div>
    </div>
</script>

// Template for time column
<script id="timetemplate" type="text/x-jsrender">
    <div style="height:100%">
        <div>
            <div>{{"{{"}}:~timeDisplay(StartTime){{}}}}</div>
        </div>
    </div>
</script>

// Template for appointment which applies for event column in agenda view.
<script id="apptemplate" type="text/x-jsrender">
    {{"{{"}}if View !== "agenda"{{}}}}
        <div style="height:100%; background-color:orange; margin-left: 5px;">
            <div style="margin-left: 2px;">{{"{{"}}:Subject{{}}}}</div>
            <div style="margin-left: 2px;">{{"{{"}}:Location{{}}}}</div>
        </div>
    {{"{{"}}else{{}}}}
        <div>{{"{{"}}:Subject{{}}}}, {{"{{"}}:Location{{}}}}</div>
    {{"{{"}}/if{{}}}}
</script>

<script type="text/javascript">
function _getDate(date) {
    var dateCol = new Date(date);
    return dateCol.toDateString();
}

function _getTime(date) {
    var time = new Date(date);
    return time.toLocaleTimeString();
}

//Here, used the helper function to get the date and time value part from the StartTime.
$.views.helpers({
    dateDisplay: _getDate,
    timeDisplay: _getTime
});
</script>
</asp:Content>

{% endhighlight %}

