---
layout: post
title: Data Binding | TreeGrid | ASP.NET | Syncfusion
description: data binding
platform: aspnet
control: TreeGrid
documentation: ug
---

# Data Binding

Data Binding is the process that establishes a connection between the application and different kinds of data sources such as business objects.

### Local Data Binding

In Local Data Binding, datasource for rendering the TreeGrid control is retrieved from the same application locally.

Two types of Data Binding are possible with TreeGrid control, 

* Hierarchical Datasource Binding
* Self-Referential Data Binding (Flat Data)

### Hierarchy Datasource Binding

The following code example shows you how to bind the Hierarchical local data into the TreeGrid control.
{% tabs %}
{% highlight c# %}

TreeGrid.aspx.cs
using Syncfusion.JavaScript;

using Syncfusion.JavaScript.Models;

using System;

using System.Collections.Generic;

using System.Data;

using System.Linq;

using System.Web;

using System.Web.UI;

using System.Web.UI.WebControls;

using WebSampleBrowser.TreeGrid.Model;

namespace WebSampleBrowser.TreeGrid

{
    public partial class TreeGridDefault : System.Web.UI.Page

    {
        protected void Page_Load(object sender, EventArgs e)

        {

            TaskDetailsCollection TaskCollection = new TaskDetailsCollection();

            this.TreeGridControlDefault.DataSource = TaskCollection.GetDataSource();

            this.TreeGridControlDefault.DataBind();

        }  

     }

    public class TaskDetailsCollection

    {

        public List<TaskDetails> GetDataSource()

        {

            List<TaskDetails> tasks = new List<TaskDetails>();





            tasks.Add(new TaskDetails()

            {

                TaskID = 1,

                TaskName = "Planning",

                StartDate = "02/03/2014",

                EndDate = "02/07/2014",

                Progress = "100",

                Duration = 5,

            });

            tasks[0].SubTasks = new List<TaskDetails>();

            tasks[0].SubTasks.Add(new TaskDetails()

            {
                TaskID = 2,

                TaskName = "Plan timeline",

                StartDate = "02/03/2014",

                EndDate = "02/07/2014",

                Duration = 5,

                Progress = "100"

            });

            tasks[0].SubTasks.Add(new TaskDetails()

            {
                TaskID = 3,

                TaskName = "Plan budget",

                StartDate = "02/03/2014",

                EndDate = "02/07/2014",

                Duration = 5,

                Progress = "100"

            });

            tasks[0].SubTasks.Add(new TaskDetails()

            {
                TaskID = 4,

                TaskName = "Allocate resources",

                StartDate = "02/03/2014",

                EndDate = "02/07/2014",

                Duration = 5,

                Progress = "100"

            });

            tasks[0].SubTasks.Add(new TaskDetails()

            {
                TaskID = 5,

                TaskName = "Planning complete",

                StartDate = "02/07/2014",

                EndDate = "02/07/2014",

                Duration = 0,

                Progress = "0"

            });

    //...

    //...
            return tasks;

        }

    }

    public class TaskDetails

    {
        public int TaskID { get; set; }

        public string TaskName { get; set; }

        public string StartDate { get; set; }

        public string EndDate { get; set; }

        public int Duration { get; set; }

        public string Progress { get; set; }

        public List<TaskDetails> SubTasks { get; set; }     

    }
}

{% endhighlight %} 

{% highlight xml %}

<%@ Page Language="C#" AutoEventWireup="true" MasterPageFile="~/Samplebrowser.Master" CodeBehind="TreeGridDefault.aspx.cs" Inherits="WebSampleBrowser.TreeGrid.TreeGridDefault" %>

<%@ Register assembly="Syncfusion.EJ" namespace="Syncfusion.JavaScript.Models" tagprefix="cc1" %>

<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

    <span class="sampleName">TreeGrid / Default</span>

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">           

       <div>                  

        <ej:TreeGrid runat="server" ID="TreeGridControlDefault" 

             ChildMapping="SubTasks" 

             TreeColumnIndex="1">

            <columns>

                <ej:TreeGridColumn HeaderText="Task Id" Field="TaskID" Width="45" />

                <ej:TreeGridColumn HeaderText="Task Name" Field="TaskName" />

                <ej:TreeGridColumn HeaderText="Start Date" Field="StartDate" />

                <ej:TreeGridColumn HeaderText="End Date" Field="EndDate" />

                <ej:TreeGridColumn HeaderText="Duration" Field="Duration" />

                <ej:TreeGridColumn HeaderText="Progress" Field="Progress" />

            </columns>            

        </ej:TreeGrid>

       </div>

</asp:Content>

<asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection">

    <style type="text/css">

        #TreeGridControlDefault{                       

            width:950px;       

        }

    </style>

</asp:Content>

{% endhighlight %}
{% endtabs %}

The output of the above steps is as follows:

 ![](Data-Binding_images/Data-Binding_img1.png)



### Self-Referential Data Binding (Flat Data)

TreeGrid is rendered from Self-Referential data structures by providing two fields: ID field and parent ID field.

* ID Field- This field contains unique values used to identify nodes. Its name is assigned to the IdMapping property.

* Parent ID Field- This field contains values that indicate parent nodes. Its name is assigned to the ParentIdMapping property.

{% tabs %}
{% highlight c# %}

TreeGrid.aspx.cs

using System.Linq;

using System.Web;

using System.Web.UI;

using System.Web.UI.WebControls;

using WebSampleBrowser.TreeGrid.Model;

namespace WebSampleBrowser.TreeGrid

{
    public partial class TreeGridDefault : System.Web.UI.Page

    {
        protected void Page_Load(object sender, EventArgs e)

        {

            TaskDetailsCollection TaskCollection = new TaskDetailsCollection();

            this.TreeGridControlDefault.DataSource = TaskCollection.GetDataSource();

            this.TreeGridControlDefault.DataBind();

        }
    }
	
    public class TaskDetails

    {
        public string StartDate { get; set; }
		
        public int Id { get; set; }

        public int ParentId { get; set; }

        public string Name { get; set; }

        public int Duration { get; set; }

        public int PercentDone { get; set; }

        public List<Data> Children { get; set; }

    }
	
    public class TaskDetailsCollection

    {

        public List<TaskDetails> GetDataSource()

        {

            List<TaskDetails> list = new List<TaskDetails>();

            list.Add(new TaskDetails()

            {

                Id = 1,

                Name = "Task 1",

                StartDate = "02/03/2014",

                Duration = 5

            });

            list.Add(new TaskDetails()

            {

                Id = 2,

                Name = " Child Task 1",

                ParentId = 1,

                StartDate = "02/03/2014",

                Duration = 5,

            });
			
            list.Add(new TaskDetails()

            {
                Id = 3,

                ParentId = 1,

                Name = "Child Task 2",

                StartDate = "02/03/2014",

                Duration = 5,

                PercentDone = 100,

            });

            list.Add(new TaskDetails()

            {
                Id = 22,

                ParentId = 2,

                Name = " Sub Child Task 1",

                StartDate = "02/03/2014",

                Duration = 5,

                PercentDone = 40,

            });

            list.Add(new TaskDetails()

            {
                Id = 23,

                ParentId = 2,

                Name = " Sub Child Task 2",

                StartDate = "02/03/2014",

                Duration = 5,

                PercentDone = 100,

            });

            list.Add(new TaskDetails()

            {
       			Id = 12,

                ParentId = 22,

                Name = " Inner Child Task 1",

                StartDate = "02/03/2014",

                Duration = 5,

            });

            list.Add(new TaskDetails()

            {
                Id = 13,

                ParentId = 22,

                Name = " Inner Child Task 2",

                StartDate = "02/03/2014",

                Duration = 5,

                PercentDone = 100,

            });

     //...

    //...
	return list;

        }
	}
}
{% endhighlight %} 

{% highlight xml %}

TreeGrid.aspx

<%@ Page Language="C#" AutoEventWireup="true" MasterPageFile="~/Samplebrowser.Master" CodeBehind="TreeGridDefault.aspx.cs" Inherits="WebSampleBrowser.TreeGrid.TreeGridDefault" %>

<%@ Register assembly="Syncfusion.EJ" namespace="Syncfusion.JavaScript.Models" tagprefix="cc1" %>

<asp:Content ID="Content1" ContentPlaceHolderID="SampleHeading" runat="server">

    <span class="sampleName">TreeGrid / Default</span>

</asp:Content>

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">           

       <div>                  

        <ej:TreeGrid runat="server" ID="TreeGridControlDefault" 

             ChildMapping="SubTasks" 

             TreeColumnIndex="1"

             IdMapping="Id"

             ParentIdMapping="ParentId">

            <columns>

                <ej:TreeGridColumn HeaderText="Task Id" Field="Id" Width="45" />

                <ej:TreeGridColumn HeaderText="Task Name" Field="Name" />

                <ej:TreeGridColumn HeaderText="Start Date" Field="StartDate" />

                <ej:TreeGridColumn HeaderText="Duration" Field="Duration" />

                <ej:TreeGridColumn HeaderText="Progress" Field="PercentDone" />

            </columns>            

        </ej:TreeGrid>

       </div>

</asp:Content>

<asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection">

    <style type="text/css">

        #TreeGridControlDefault{                       

            width:950px;       

        }

    </style>

</asp:Content>

{% endhighlight %}
{% endtabs %}

The following screenshot shows the output of the above steps,

![](Data-Binding_images/Data-Binding_img2.png) 