---
layout: post
title: Swimlanes with Kanban widget for Syncfusion Essential ASP.NET
description: How to enable Kanban with Swimlanes
platform: aspnet
control: Kanban
documentation: ug
--- 
# Swim lanes

Swim lanes are a horizontal categorization of issues in the Kanban control which brings transparency to the workflow. This can be enabled by mapping the `SwimlaneKey` to appropriate column name in the `DataSource`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

  	<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Testing" Key="Testing" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" ImageUrl="ImgUrl" SwimlaneKey="Assignee" />
   </ej:Kanban>     

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy Davloio", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven walker", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael Suyama", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert King", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura Callahan", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy Davloio", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret hamilt", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven walker", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael Suyama", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert King", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura Callahan", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret hamilt", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Swimlanes_images/Swimlanes_img1.png)

# Drag And Drop between swim lanes

You can set `AllowDragAndDrop` property of `SwimlaneSettings` as true to enable Drag and Drop between the swim lanes.

If a card is to be dragged in the same swim lane, only a droppable target cell is added to the dotted line border. If a card is dragged from one swim lane to another, all the Kanban cells will be added to the dotted line borders, except the dragged card cell.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="KanbanBoard" runat="server" AllowSelection="false" AllowTitle="true" KeyField="Status">
        <Columns>
            <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
            <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
            <ej:KanbanColumn HeaderText="Testing" Key="Testing" />
            <ej:KanbanColumn HeaderText="Done" Key="Close" />
        </Columns>
        <Fields Content="Summary" ImageUrl="ImgUrl" PrimaryKey="Id" SwimlaneKey="Assignee" />
        <SwimlaneSettings AllowDragAndDrop="true" />
   </ej:Kanban>
  
{% endhighlight  %}

{% highlight c# %}

      List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy Davloio", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven walker", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael Suyama", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert King", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura Callahan", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy Davloio", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret hamilt", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven walker", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael Suyama", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert King", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura Callahan", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret hamilt", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Swimlanes_images/Swimlanes_img2.png)

# Unassigned swim lane group

Kanban cards which have null,undefined, empty string("") swimlane key values or user specified swimlane key values in the `Keys(SwimlaneSettings.UnassignedGroup.Keys)` collection will be grouped under the Unassigned swimlane group.You can enable and disble this behavior using the property `Enable(SwimlaneSettings.UnassignedGroup.Enable)` and the default value is `true`.
  
Default values in the `Keys(SwimlaneSettings.UnassignedGroup.Keys)` collection are null,undefined,empty string("").You can also add your own(user-defined) swim-lane key values in the `Keys(SwimlaneSettings.UnassignedGroup.Keys)` collection.
  
## Unassigned swim lane group with default values

Kanban cards which have null,undefined, empty string("") swimlane key values will be grouped under the Unassigned swimlane group when Unassigned swim lane group is enabled.(set `true` to `Enable(SwimlaneSettings.UnassignedGroup.Enable)` property and the default value is `true`).

Default values in the `Keys(SwimlaneSettings.UnassignedGroup.Keys)` collection are null,undefined,empty string("").

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

  	<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" ImageUrl="ImgUrl" SwimlaneKey="Assignee" />
   </ej:Kanban>     

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "", "", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, null, "", 2));
            Task.Add(new Tasks(5, "Close", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "", "", 1));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Swimlanes_images/Swimlanes_img3.png)

## Unassigned swim lane group with user specified values

User specified swimlane key values in the `Keys(SwimlaneSettings.UnassignedGroup.Keys)` collection will be grouped under the Unassigned swimlane group when Unassigned swim lane group is enabled.(set `true` to `Enable(SwimlaneSettings.UnassignedGroup.Enable)` propertyproperty and the default value is `true`).

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

  	<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
        <Columns>
            <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
            <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
            <ej:KanbanColumn HeaderText="Done" Key="Close" />
        </Columns>
        <SwimlaneSettings>
            <UnassignedGroup Keys="Andrew Fuller, ,null" />
        </SwimlaneSettings>
        <Fields Content="Summary" ImageUrl="ImgUrl" SwimlaneKey="Assignee" />
    </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy Davloio", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "", "", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, null, "", 2));
            Task.Add(new Tasks(5, "Close", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "", "", 1));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Swimlanes_images/Swimlanes_img4.png)

## Enable/Disable unassigned swim lane group

You can enable and disble the unassigned swim lane group using the property `Enable(SwimlaneSettings.UnassignedGroup.Enable)` and the default value is `true`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

  	 <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
        <Columns>
            <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
            <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
            <ej:KanbanColumn HeaderText="Done" Key="Close" />
        </Columns>
        <SwimlaneSettings>
            <UnassignedGroup Enable="false" />
        </SwimlaneSettings>
        <Fields Content="Summary" ImageUrl="ImgUrl" SwimlaneKey="Assignee" />
    </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew Fuller", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, null, "", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, null, "", 2));
            Task.Add(new Tasks(5, "Close", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, null, "", 1));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Swimlanes_images/Swimlanes_img5.png)