---
layout: post
title: Resource Allocation View
description: resource allocation view
platform: aspnet
control: Gantt
documentation: ug
---

# Resource Allocation View
Resource allocation view is used to visualize the resource usage in a project. Resources are displayed in separate rows and all the tasks assigned to a specific resource will be displayed in the chart side. In this view, a user can able to easily identify the overallocation of resources in a project.

![](Resource-Allocation-View_images/ResourceView_1.png)

## Data Binding
User can bind two types of data structure to Gantt in resource allocation view,

* Hierarchical data source binding
* Flat data binding

### Hierarchical data source binding
The following code example explains how to bind the hierarchical data.

{% highlight html %}

<ej:Gantt ID="ResourceViewGantt" runat="server" ViewType="ResourceView"
    ResourceNameMapping="ResourceName" TaskCollectionMapping="Tasks" TaskIdMapping="TaskID"
    ...>
</ej:Gantt>

{% endhighlight %}

{% highlight c# %}

public class TaskDetails
{
    public int TaskID { get; set; }
    public string TaskName { get; set; }
    public string StartDate { get; set; }
    public string EndDate { get; set; }
    public int Duration { get; set; }
    public string Progress { get; set; }
    public List<TaskDetails> SubTasks { get; set; }
    public List<object> ResourceID { get; set; }
    public string Predecessors { get; set; }
}

public class ResourceDetails
{
    public string ResourceName { get; set; }
    public List<TaskDetails> Tasks { get; set; }
}

public List<ResourceDetails> GetResourceData()
{
    List<ResourceDetails> data = new List<ResourceDetails>() {
    new ResourceDetails()
    {
        ResourceName = "Anne Dodsworth",
        Tasks = new List<TaskDetails>()
        {
            new TaskDetails() { TaskID = 1, TaskName= "Plan timeline", StartDate= "02/06/2017", EndDate = "02/10/2017", Duration= 5, Progress= "50"},
            new TaskDetails() { TaskID= 2, TaskName= "Plan budget", StartDate= "02/13/2017", EndDate= "02/17/2017", Duration= 5, Progress= "50"},
            new TaskDetails() { TaskID= 3, TaskName= "Allocate resources", StartDate= "02/20/2017", EndDate= "02/24/2017", Duration= 5, Progress= "0"}
        }
    }
    };
    //...
    return data;
}

protected void Page_Load(object sender, EventArgs e)
{
    this.ResourceViewGantt.DataSource = GetResourceData();
    this.ResourceViewGantt.DataBind();
}

{% endhighlight %}

### Flat data binding
The following code example explains how to bind the flat data.

{% highlight html %}

<ej:Gantt ID="ResourceViewGantt" runat="server" ViewType="ResourceView" ResourceIdMapping="ResourceId"            ResourceInfoMapping="ResourceID" ResourceNameMapping="ResourceName" TaskIdMapping="TaskID"
    ...>
</ej:Gantt>

{% endhighlight %}

{% highlight c# %}

    public class TaskDetails
    {
        public int TaskID { get; set; }
        public string TaskName { get; set; }
        public string StartDate { get; set; }
        public string EndDate { get; set; }
        public int Duration { get; set; }
        public string Progress { get; set; }
        public string Priority { get; set; }
        public bool Approved { get; set; }  
        public List<TaskDetails> SubTasks { get; set; }
        public List<Object> ResourceID{ get; set; }
        public bool IsManual { get; set; }
    }

    public class GanttResources
    {
        public string ResourceName { get; set; }
        public int ResourceId { get; set; }
        public int TeamId { get; set; }
    }

    public List<GanttResources> GetResources()
    {
        List<GanttResources> data = new List<GanttResources>(){
            new GanttResources(){ ResourceId = 1, ResourceName = "Anne Dodsworth" },
            new GanttResources(){ ResourceId = 2, ResourceName = "David William"},
            new GanttResources(){ ResourceId = 3, ResourceName = "Nancy Davolio"},
            //...
        };
        return data;
    }

    public List<TaskDetails> GetResourceFlatData()
    {
        List<TaskDetails> data = new List<TaskDetails>() {
            new TaskDetails() { TaskID = 1, TaskName= "Plan timeline", StartDate= "02/06/2017", EndDate = "02/10/2017", Duration= 5, Progress= "50", ResourceID= new List<object>(){1}},
            new TaskDetails() { TaskID= 2, TaskName= "Plan budget", StartDate= "02/13/2017", EndDate= "02/17/2017", Duration= 5, Progress= "50", ResourceID= new List<object>(){1}},
            new TaskDetails() { TaskID= 3, TaskName= "Allocate resources", StartDate= "02/20/2017", EndDate= "02/24/2017", Duration= 5, Progress= "0", ResourceID= new List<object>(){1}},
            //..
        }
        return data;
    }    

    protected void Page_Load(object sender, EventArgs e)
    {
        this.ResourceViewGantt.DataSource = GetResourceFlatData();
        this.ResourceViewGantt.Resources = GetResources();
        this.ResourceViewGantt.DataBind();
    }
{% endhighlight %}

![](Resource-Allocation-View_images/ResourceView_2.png)

## Grouping
The resources and the tasks assigned to those resources can be grouped into categories. The property `GroupCollection` is used to define the groups to be displayed in the project. The properties `GroupIdMapping` and `GroupNameMapping` are used to map the group details.

The below code snippet explains grouping of the resources in resource allocation view.

{% highlight html %}

<ej:Gantt ID="ResourceViewGantt" runat="server" ViewType="ResourceView" GroupIdMapping="TeamId"        GroupNameMapping="TeamName" ResourceIdMapping="ResourceId" ResourceInfoMapping="ResourceID"  ResourceNameMapping="ResourceName" TaskIdMapping="TaskID"
 ...>
</ej:Gantt>

{% endhighlight %}

{% highlight c# %}

 public class TaskDetails
    {
        public int TaskID { get; set; }
        public string TaskName { get; set; }
        public string StartDate { get; set; }
        public string EndDate { get; set; }
        public int Duration { get; set; }
        public string Progress { get; set; }
        public string Priority { get; set; }
        public bool Approved { get; set; }  
        public List<TaskDetails> SubTasks { get; set; }
        public List<Object> ResourceID{ get; set; }
        public bool IsManual { get; set; }
    }

    public class GanttResources
    {
        public string ResourceName { get; set; }
        public int ResourceId { get; set; }
        public int TeamId { get; set; }
    }

    public List<GanttResources> GetResources()
    {
        List<GanttResources> data = new List<GanttResources>(){
            new GanttResources(){ ResourceId = 1, ResourceName = "Anne Dodsworth",TeamId=1 },
            new GanttResources(){ ResourceId = 2, ResourceName = "David William", TeamId=1},
            new GanttResources(){ ResourceId = 3, ResourceName = "Nancy Davolio", TeamId=2},
            //...
        };
        return data;
    }

    public class ResourceGroupDetails
    {
        public string TeamName { get; set; }
        public int TeamId { get; set; }
    }

    public List<ResourceGroupDetails> GetResourceGroups()
    {
        List<ResourceGroupDetails> data = new List<ResourceGroupDetails>(){
            new ResourceGroupDetails(){ TeamName="Planning Team", TeamId=1},
            new ResourceGroupDetails(){ TeamName="Development Team", TeamId=2},
            new ResourceGroupDetails(){ TeamName="Testing Team", TeamId=3}
        };
        return data;
    }

    public List<TaskDetails> GetResourceFlatData()
    {
        List<TaskDetails> data = new List<TaskDetails>() {
            new TaskDetails() { TaskID = 1, TaskName= "Plan timeline", StartDate= "02/06/2017", EndDate = "02/10/2017", Duration= 5, Progress= "50", ResourceID= new List<object>(){1}},
            new TaskDetails() { TaskID= 2, TaskName= "Plan budget", StartDate= "02/13/2017", EndDate= "02/17/2017", Duration= 5, Progress= "50", ResourceID= new List<object>(){1}},
            new TaskDetails() { TaskID= 3, TaskName= "Allocate resources", StartDate= "02/20/2017", EndDate= "02/24/2017", Duration= 5, Progress= "0", ResourceID= new List<object>(){1}},
            //..
        }
        return data;
    }    

    protected void Page_Load(object sender, EventArgs e)
    {
        this.ResourceViewGantt.DataSource = GetResourceFlatData();
        this.ResourceViewGantt.GroupCollection = GetResourceGroups();
        this.ResourceViewGantt.Resources = GetResources(); 
        this.ResourceViewGantt.DataBind();
    }

{% endhighlight %}

The below screen shot depicts a resource view in a project with 3 groups.

![](Resource-Allocation-View_images/ResourceView_3.png)

## CRUD data operations

### Adding a task
It is possible to add a task dynamically either by using toolbar insert icon or by context menu add option. The below screen shot shows the toolbar add and context menu add options.

![](Resource-Allocation-View_images/ResourceView_4.png)

![](Resource-Allocation-View_images/ResourceView_5.png)

When the insert option is clicked, the add dialog will be displayed prompting the user to provide the task details. After providing the task details, when user click the save button without providing the resource information or without assigning any resource to the task, the task will be added at the top by default.

![](Resource-Allocation-View_images/ResourceView_6.png)

![](Resource-Allocation-View_images/ResourceView_7.png)

If the newly added task should be assigned to a specific resource, user can able to select the resource information in the resource tab of add dialog.

![](Resource-Allocation-View_images/ResourceView_8.png)

The below screen shot depicts a new task being assigned to a resource `Anne Dodsworth`.

![](Resource-Allocation-View_images/ResourceView_9.png)

N> It is not possible to add a resource to the project dynamically.
N> A task can be assigned to one or more resource while adding.

### Editing

#### Editing a Task
A task can be edited either by using edit dialog or by mouse interactions. A user can edit a task using edit dialog by performing double click action on the taskbar, user can then edit the task information in the edit dialog.

![](Resource-Allocation-View_images/ResourceView_10.png)
![](Resource-Allocation-View_images/ResourceView_11.png)

A task’s schedule can be changed by left resizing, right resizing or dragging the task across the dates.

![](Resource-Allocation-View_images/ResourceView_12.png)

#### Update task values dynamically
In resource allocation view also, we can update the task details dynamically on any action like external button click by using [`updateRecordByTaskId`](/api/js/ejgantt#methods:updaterecordbytaskid "updateRecordByTaskId(data)") method. The below code example explains how to use this method in resource allocation view.

{% highlight html %}

<ej:Gantt ID="ResourceViewGantt" ClientIDMode="Static" runat="server" ViewType="ResourceView"
 ...>
</ej:Gantt>
<button id="update" onclick="updateTask()">Update Tasks</button>

<script type="text/javascript">

function updateTask() {
    var ganttObject = $("#ResourceViewGantt").ejGantt("instance");
    var task = {};
    task.TaskID = 3;
    task.ResourceID = [1, 2, 3];
    task.StartDate = new Date("02/25/2017")
    task.Duration = 10;
    task.TaskName = task.TaskID + " - Name Changed";
    ganttObject.updateRecordByTaskId(task);
}
</script>

{% endhighlight %}

The below screenshot shows the result of above code example.

![](Resource-Allocation-View_images/ResourceView_19.png)
Before update
{:.caption}

![](Resource-Allocation-View_images/ResourceView_20.png)
After update
{:.caption}

### Deleting

#### Deleting Task
User should select a task to be removed from the project, and then the task can be deleted using context menu delete button.

![](Resource-Allocation-View_images/ResourceView_13.png)

#### Deleting Resource
User can able to delete a resource and the tasks assigned to it using toolbar and context menu delete options. After selecting the resource row, when clicking the delete toolbar icon, the resource will be removed from the project and the tasks assigned to that resource will be listed in unassigned tasks’ list. The same will happen for context menu delete option.

![](Resource-Allocation-View_images/ResourceView_14.png)

The below screen shot depicts the tasks of the removed resource added as unassigned tasks to the project.

![](Resource-Allocation-View_images/ResourceView_15.png)

## Unassigned Tasks and Resources
There may be some instances, where one or more resources are not yet included in the project plan. Therefore, those resources are left with no tasks assigned to them. Those resources are termed as `unassigned resource`. The right side of the resource row will be left blank with no tasks.
The below code snippet shows a resource with no tasks assigned to it.

{% highlight c# %}

public List<ResourceDetails> GetResourceData()
{
    List<ResourceDetails> data = new List<ResourceDetails>() {
    new ResourceDetails()
    {
        ResourceName = "Anne Dodsworth",
        Tasks = new List<TaskDetails>()
        {
            new TaskDetails() { TaskID = 1, TaskName= "Plan timeline", StartDate= "02/06/2017", EndDate = "02/10/2017", Duration= 5, Progress= "50"},
            new TaskDetails() { TaskID= 2, TaskName= "Plan budget", StartDate= "02/13/2017", EndDate= "02/17/2017", Duration= 5, Progress= "50"},
            new TaskDetails() { TaskID= 3, TaskName= "Allocate resources", StartDate= "02/20/2017", EndDate= "02/24/2017", Duration= 5, Progress= "0"}
        }
    },
    new ResourceDetails()
    {
        ResourceName = "Nancy Davolio",
        Tasks = new List<TaskDetails>() {}
    }
    //...
    };
    return data;
}
{% endhighlight %}

In the below screen shot, the resource `Nancy Davolio` is the unassigned resource.

![](Resource-Allocation-View_images/ResourceView_16.png)

There may be instances where some tasks are not yet assigned with resources. Those tasks that are not assigned to any resources are termed as unassigned tasks. Unassigned tasks are displayed at bottom, with resource name as `Unassigned Task`. Unassigned tasks can be assigned to any resources in the project.
The below code snippet shows a task with no resource assigned to it.

{% highlight c# %}

    public class GanttResources
    {
        public string ResourceName { get; set; }
        public int ResourceId { get; set; }
        public int TeamId { get; set; }
    }

    public List<GanttResources> GetResources()
    {
        List<GanttResources> data = new List<GanttResources>(){
            new GanttResources(){ ResourceId = 1, ResourceName = "Anne Dodsworth",TeamId=1 },
            new GanttResources(){ ResourceId = 2, ResourceName = "David William", TeamId=1},
            new GanttResources(){ ResourceId = 3, ResourceName = "Nancy Davolio", TeamId=2},
            //...
        };
        return data;
    }

    public List<TaskDetails> GetResourceFlatData()
    {
        List<TaskDetails> data = new List<TaskDetails>() {
            //...
            new TaskDetails() { TaskID= 2, TaskName= "Plan budget", StartDate= "02/13/2017", EndDate= "02/17/2017", Duration= 5, Progress= "50"},
            //..
        }
        return data;
    }  
{% endhighlight %}

In the below screen shot, there more instances of unassigned tasks.

![](Resource-Allocation-View_images/ResourceView_17.png)

## Resource Overallocation
By default, a resource can work 8 hours a work day, but when a resource is forced to work more than 8 hours it is termed as overallocation. Or when a resource is assigned with two or more tasks which is occurring in a same date range, this state is termed as over allocation for a resource. The overlapped tasks are highlighted like in the below screen shot. The overlapped tasks will be displayed one below the other with an overlapped highlighted region.

![](Resource-Allocation-View_images/ResourceView_18.png)