---
layout: post
title: Getting Started | Kanban | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Kanban
documentation: ug
---

# Getting Started

This section explains briefly about how to create a Kanban in your application with ASP.NET.

## Create your first Kanban ASP.NET Web Forms Application

You can create a Kanban with a highly customizable look and feel. This section describes how you can customize, filter and group cards.

1. Create a Syncfusion ASP.NET Web Forms application.
2. Add a Kanban in the Index.aspx page. 



3. By Columns definition, the Is Collapsed property is used in the column collapse or expand state. The Width property is used to define the width of the columns. The Header text property is used to render the Kanban with specified columns header text. The Key property is used to render the Kanban with specified columns key.

4. Configure the Kanban control with SQL data source using smart tag.

   

  {% highlight html %}
	   <ej:Kanban ID="Kanban1" runat="server" DataSourceID="SqlDataSource1">
       </ej:Kanban>
       <asp:SqlDataSource runat="server" ID="SqlDataSource1" ConnectionString='<%$ ConnectionStrings:NORTHWNDConnectionString %>' SelectCommand="SELECT * FROM [Tasks]"></asp:SqlDataSource>
 {% endhighlight %}
   
   N> Create a connection string in Web.config file using SQL database.

  {% highlight html %}
		<connectionStrings>
          <add name="NORTHWNDConnectionString" connectionString="Data Source=(LocalDB)\v11.0;AttachDbFilename=|DataDirectory|\NORTHWND.MDF;Integrated Security=True" providerName="System.Data.SqlClient" />
        </connectionStrings>
 {% endhighlight %}
 
   For more information about SQL data source configuration refer the following link: [http://msdn.microsoft.com/en-us/library/vstudio/w1kdt8w2(v=vs.100).aspx](http://msdn.microsoft.com/en-us/library/vstudio/w1kdt8w2(v=vs.100).aspx)
   
   ![](Getting-Started_images/Getting_Started_img1.png) 

## Data Binding

`Data binding` in the Kanban is achieved by using the [ej.DataManager](http://help.syncfusion.com/aspnet/datamanager/overview)  that supports both RESTful JSON data services binding and local JSON array binding. To set the data source to Kanban, the `DataManager` property is assigned with the instance of the `ej.DataManger`. 

{% highlight html %}

 <ej:Kanban ID="Kanban" runat="server">
                <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks" />
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" />
                    <ej:KanbanColumn HeaderText="In Progress" />
                    <ej:KanbanColumn HeaderText="Done" />
                </Columns>
  </ej:Kanban>

{% endhighlight %}

![](Getting-Started_images/Getting_Started_img2.png) 

N> ODataAdaptor is the default adaptor used within DataManager. While binding to other web services, proper [data adaptor](http://help.syncfusion.com/aspnet/datamanager/data-adaptors) needs to be set for `adaptor` option of DataManager.

## Mapping Values

In order to display cards in Kanban control, you need to map the database fields to Kanban cards and columns. The required mapping field are listed as follows.

 * KeyField - Map the column name to use as `Key` values to columns.
 * Columns -  Map the corresponding `Key` values of `KeyField` column to each columns.
 * Content - Map the column name to use as content to cards.
 * PrimaryKey - Map the column name to use as primary Key.

{% highlight html %}

<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks" />
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
 </ej:Kanban>

{% endhighlight  %}

![](Getting-Started_images/Getting_Started_img3.png) 

N> `PrimaryKey` field is mandatory for “Drag and Drop”, ”Selection” and “Editing” Features.

## SwimlaneKey

`SwimlaneKey` can be enabled by mapping the `SwimlaneKey` to appropriate column name in `DataManager`. This enables the grouping of the cards based on the mapped column values.

{% highlight html %}

<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks" />
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" SwimlaneKey="Assignee" />
</ej:Kanban>

{% endhighlight %}

![](Getting-Started_images/Getting_Started_img4.png) 

## Adding Filters

Filters allows to filter the collection of cards from `DataManager` which meets the predefined `Query ` in the filters collection. To enable filtering, define `FilterSettings` collection with display `Text` and [ej.Query](http://help.syncfusion.com/aspnet/datamanager/query).

{% highlight html %}

<ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks" />
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" SwimlaneKey="Assignee" />
                <FilterSettings>
                    <ej:KanbanFilterSetting Text="Janet Issues" Query="new ej.Query().where('Assignee', 'equal', 'Janet Leverling')" Description="Displays issues which matches the assignee as 'Janet Leverling" />
                    <ej:KanbanFilterSetting Text="Testing Issues" Query="new ej.Query().where('Status', 'equal', 'Testing')" Description="Display the issues of 'Testing'" />
                </FilterSettings>
 </ej:Kanban>

{% endhighlight %}

![](Getting-Started_images/Getting_Started_img5.png)  