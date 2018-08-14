---
layout: post
title: Getting Started with TreeView | TreeView | ASP.NET | Syncfusion
description: To get start with TreeView by adding references
platform: aspnet
control: TreeView
documentation: UG
---

# Getting started
	
This section explains briefly about how to create a TreeView in ASP.NET Web platform.

## Create your first TreeView in ASP.NET Web

Create an ASP Web application and add necessary assemblies, CSS and scripts with the help of the given [ASP.NET Web-Getting Started ](http://help.syncfusion.com/aspnet/getting-started#) documentation. After creating this project, you can create a TreeView in following ways.

## TreeView using “Nodes” Property

You can create a tree using “Nodes” property of TreeView control. Here there is no necessary to use a data source for rendering TreeView.

In the view page, add an element to render the TreeView with specified items.
    
    {% highlight html %}
    
    <ej:TreeView ID="treeview" runat="server" Width="400px">
            <Nodes>
                <ej:TreeViewNode Expanded="True" Text="Item 1">
                    <Nodes>
                        <ej:TreeViewNode Text="Item 1.1">
                            <Nodes>
                                <ej:TreeViewNode Text="Item 1.1.1"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Item 1.1.2"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Item 1.2">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
    
                <ej:TreeViewNode Text="Item 2"></ej:TreeViewNode>
    
                <ej:TreeViewNode Text="Item 3"></ej:TreeViewNode>
            </Nodes>
        </ej:TreeView>
    
    {% endhighlight %}
    
## Tree View using Data Binding

Another way of creating TreeView is binding with the data source, you can bind local data source to create a TreeView. 

The [beforeLoad](https://help.syncfusion.com/api/js/ejtreeview#events:beforeload) event will be triggered before loading nodes into TreeView.

Render TreeView with local data source.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to the DataSource property of TreeView.
    
    {% highlight c# %}
    
    //Define local DataSource elements by using the ID, ParentID, Text and HasChild fields in code behind and map the list data to DataSource property.
        public partial class DefaultFunctionalities : System.Web.UI.Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                this.treeview.DataSource = new TreeLocalDataSource().GetTreeDataItems().ToList();
            }
        }
        public class TreeLocalDataSource
        {
    
            public TreeLocalDataSource() { }
    
            public TreeLocalDataSource(int _id, int _parentId, string _text, string _hasChild)
            {
    
                this.ID = _id;
    
                this.ParentID = _parentId;
    
                this.Text = _text;
    
                this.HasChild = _hasChild;
    
            }
    
            [Browsable(true)]
    
            public int ID
            {
    
                get;
    
                set;
    
            }
    
            [Browsable(true)]
    
            public int ParentID
            {
    
                get;
    
                set;
    
            }
    
    
    
            [Browsable(true)]
    
            public string Text
            {
    
                get;
    
                set;
    
            }
    
            [Browsable(true)]
    
            public string HasChild
            {
    
                get;
    
                set;
    
            }
    
            public List<TreeLocalDataSource> GetTreeDataItems()
            {
    
                List<TreeLocalDataSource> data = new List<TreeLocalDataSource>();
    
                data.Add(new TreeLocalDataSource(1, 0, "Item 1", "true"));
    
                data.Add(new TreeLocalDataSource(2, 1, "Item 1.1", ""));
    
                data.Add(new TreeLocalDataSource(3, 1, "Item 1.2", ""));
    
                data.Add(new TreeLocalDataSource(4, 1, "Item 1.3", ""));
    
                data.Add(new TreeLocalDataSource(5, 0, "Item 2", "true"));
    
                data.Add(new TreeLocalDataSource(6, 5, "Item 2.1", "true"));
    
                data.Add(new TreeLocalDataSource(7, 5, "Item 2.2", ""));
    
                data.Add(new TreeLocalDataSource(8, 6, "Item 2.1.1", ""));
    
                data.Add(new TreeLocalDataSource(9, 0, "Item 3", ""));
                
                return data;
    
            }
    
        }
        
    {% endhighlight %}
    
In the view page, add an element and map the properties defined to the corresponding fields in data source.
    
    {% highlight html %}
    
        <%--In the Design page, assign the values for DataTextField, DataIdField, 
            DataParentIdField, DataHasChildField.--%>
        <ej:TreeView
            ID="treeview"
            runat="server"
            DataTextField="Text"
            DataIdField="ID"
            DataParentIdField="ParentID"
            DataHasChildField="HasChild">
        </ej:TreeView>
        
    {% endhighlight %}

## Create Instance for TreeView

You can create an instance for existing TreeView in following ways. Once a reference has been established, you can use the [API’s](http://help.syncfusion.com/js/api/ejtreeview#) of TreeView to control its behavior.
    
    {% highlight html %}
    
    <script type="text/javascript">
        //Specify this after your TreeView creation
        //create instance for TreeView
        var treeObj = $("#<%= treeView.ClientID %>").ejTreeView('instance');
        //or
        var treeObj1 = $("#<%= treeView.ClientID %>").data("ejTreeView");
    </script>
    
    {% endhighlight %}
    
N>**To configure the API settings after TreeView creation, please refer [API configuration](http://help.syncfusion.com/js/api-configuration#), [Invoking Methods](http://help.syncfusion.com/js/invoking-methods#).** 

## TreeView events

Essential ASP.NET Web TreeView supports all the client side [events](http://help.syncfusion.com/js/api/ejtreeview#events) which is available in EJ TreeView. Refer following code example to specify an event using EJ Web TreeView element. See Also: [Server Side Events](#_Server_Side_Events).
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            ClientSideOnNodeExpanded="onNodeExpanded"
            ClientSideOnNodeCollapsed="onNodeCollapsed"
            ClientSideOnNodeSelected="onNodeSelected">
        </ej:TreeView>
        <script type="text/javascript">
            function onNodeCollapsed(args) {
                //Handle the node collapse event
            }
    
            function onNodeExpanded(args) {
                //Handle the node expand event
            }
    
            function onNodeSelected(args) {
                //Handle the node select event
            }
        </script>
        
    {% endhighlight %}
 