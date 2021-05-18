---
layout: post
title: Filtering with Kanban widget for Syncfusion Essential ASP.NET
description: This section explains how to enable filtering and its functionalities using the Syncfusion ASP.NET Web Forms Kanban component.
platform: aspnet
control: Kanban
documentation: ug
---
# Filtering

Filtering allows to filter the collection of cards from `DataSource` which meets the predefined `Query` in the quick filters collection. To enable filtering, define `FilterSettings` collection with display `Text` and `Query`.   

You can also define display tip to describe filter definition to user using property `Description` . If the `Description` property is not defined, given `Text` will act as display tip.

We can also customize filter option through external button or `CustomToolBarItems` by using `filterCards()` method.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
    
   <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <FilterSettings>
                    <ej:KanbanFilterSetting Text="Janet Issues" Query="new ej.Query().where('Assignee', 'equal', 'Janet Leverling')" Description="Displays issues which matches the assignee as 'Janet Leverling" />
                    <ej:KanbanFilterSetting Text="Testing Issues" Query="new ej.Query().where('Status', 'equal', 'Testing')" Description="Display the issues of 'Testing'" />
                </FilterSettings>
                <Fields Content="Summary" PrimaryKey="Id" Tag="Tags" />
     </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }
           public class Tasks
           {
              public Tasks()
              {
              }
              public Tasks(int Id, string Status, string Summary, string Type, string Priority, string Tags, double Estimate, string Assignee, string ImgUrl, int RankId)
              {
                  this.Id = Id;
                  this.Status = Status;
                  this.Summary = Summary;
                  this.Type = Type;
                  this.Priority = Priority;
                  this.Tags = Tags;
                  this.Estimate = Estimate;
                  this.Assignee = Assignee;
                  this.ImgUrl = ImgUrl;
                  this.RankId = RankId;
              }
              public int Id { get; set; }
              public string Status { get; set; }
              public string Summary { get; set; }
              public string Type { get; set; }
              public string Priority { get; set; }
              public string Tags { get; set; }
              public double Estimate { get; set; }
              public string Assignee { get; set; }
              public string ImgUrl { get; set; }
              public int RankId { get; set; }
          }
           
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Filtering image1](Filtering_images/Filtering_img1.png)