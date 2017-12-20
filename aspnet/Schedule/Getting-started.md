---
title: Getting started with Schedule component	
description: Rendering a basic Scheduler with remote data
platform: aspnet
control: schedule
documentation: ug
keywords: ejschedule, schedule, schedule widget, js schedule 
---
# Getting Started

Follow the steps mentioned in the [Getting Started](http://help.syncfusion.com/aspnet/getting-started#manual-integration-of-syncfusion-aspnet-controls-into-the-newexisting-application) page of the Introduction part to create an ASP.NET application with the required assemblies, scripts and stylesheet reference.
Simply drag and drop the Scheduler control into the designer area to add it into the application, so that the following Schedule rendering code gets automatically generated in the Source code section.

{% highlight html %}

<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
    <ej:Schedule ID="Schedule" runat="server"></ej:Schedule>
</asp:Content>

{% endhighlight %}

N> Schedule control and other Syncfusion controls are configured to available by default in the Visual Studio Toolbox, if the Essential Studio package got installed on your machine.

Add a class file and place it under *App_Code* folder of your project. Create a class with Scheduler data definition as shown below within that newly added class file, which needs to be passed to the Scheduler later,

{% highlight c# %}

public class SampleData
{
    public int ProgramId { get; set; }
    public string ProgramName { get; set; }
    public string Comments { get; set; }
    public DateTime ProgramStartTime { get; set; }
    public DateTime ProgramEndTime { get; set; }
    public bool IsAllDay { get; set; }
    public bool IsRecurrence { get; set; }
    public string RecurrenceRule { get; set; }
}

{% endhighlight %}

Now create another class (*ScheduleData*) within the class file and make use of the instance of the previously created class (*SampleData*) within it and add the list of Scheduler data to it, which will then be bound to the Scheduler dataSource.

{% highlight c# %}

public class SchedulerData
{
    [DataObjectMethod(DataObjectMethodType.Select)]
    public List<SampleData> GetRecords()
    {
        List<SampleData> data = new List<SampleData> {
                new SampleData {
                    ProgramName = "Turtle Walk",
                    Comments = "Night out with turtles",
                    ProgramStartTime = new DateTime(2016, 6, 2, 3, 0, 0),
                    ProgramEndTime = new DateTime(2016, 6, 2, 4, 0, 0),
                    IsAllDay = true
                },
                new SampleData {
                    ProgramName = "Winter Sleepers",
                    Comments = "Long sleep during winter season",
                    ProgramStartTime = new DateTime(2016, 6, 3, 1, 0, 0),
                    ProgramEndTime = new DateTime(2016, 6, 3, 2, 0, 0)
                },
                new SampleData {
                    ProgramName = "Estivation",
                    Comments = "Sleeping in hot season",
                    ProgramStartTime = new DateTime(2016, 6, 4, 3, 0, 0),
                    ProgramEndTime = new DateTime(2016, 6, 4, 4, 0, 0)
                }
            };
        return data;
    }
}

{% endhighlight %}

N> To make use of the *DataObjectMethod* in your current page, need to define the namespace using `System.ComponentModel;` at the top of the page.

Now to bind the above defined data to the Scheduler, drag and drop the **ObjectDataSource** from the toolbox into the design area which generates the following code,

 ![](getting-started_images/toolbox-VS.png)
 
{% highlight html %}

<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
    <ej:Schedule ID="Schedule1" runat="server"></ej:Schedule>
    <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" >   
    </asp:ObjectDataSource>
</asp:Content>

{% endhighlight %}

Set the **SelectMethod** property of the _ObjectDataSource_ pointing to the **GetRecords** method defined within the SchedulerData Class in code page. Also set the *TypeName* property of the ObjectDataSource with the appropriate class name *SchedulerData* (including the namespace name) and map the ID of the ObjectDataSource with the Scheduler’s DataSourceID as shown below,

{% highlight html %}

<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
    <ej:Schedule ID="Schedule1" DataSourceID="ObjectDataSource1" runat="server"></ej:Schedule>
    <asp:ObjectDataSource ID="ObjectDataSource1" TypeName="NameSpace.SchedulerData" SelectMethod="GetRecords" runat="server" > </asp:ObjectDataSource>
</asp:Content>

{% endhighlight %}

N> In TypeName="NameSpace.SchedulerData" replace the `NameSpace` with the namespace name where the *SchedulerData* class is defined.

Map the Scheduler data fields with the appropriate appointmentSettings properties as shown below,

{% highlight html %}

<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
    <ej:Schedule ID="Schedule1" DataSourceID="ObjectDataSource1" runat="server">
            <AppointmentSettings Id="ProgramId" Subject="ProgramName" AllDay="IsAllDay" StartTime="ProgramStartTime" EndTime="ProgramEndTime" Description="Comments" Recurrence="IsRecurrence" RecurrenceRule="RecurrenceRule"/>
    </ej:Schedule>
    <asp:ObjectDataSource ID="ObjectDataSource1" TypeName="SchedulerData" SelectMethod="GetRecords" runat="server"> </asp:ObjectDataSource>
</asp:Content>

{% endhighlight %}

To bind the data from database or any other dataSources, refer [here](/aspnet/schedule/data-binding).


![](Getting-Started_images/Getting-Started_img1.png)
