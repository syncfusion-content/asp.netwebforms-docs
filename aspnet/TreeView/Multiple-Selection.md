---
layout: post
title: TreeView with Multiple Selection option | TreeView | ASP.NET | Syncfusion
description: Specify multiple selection option in TreeView and its settings
platform: aspnet
control: TreeView
documentation: UG
---


# Multiple Selection

TreeView supports to select the multiple nodes by specifying [allowMultiSelection](http://help.syncfusion.com/js/api/ejtreeview#members:allowmultiselection) as true. It allows you to select more than one nodes in TreeView.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.

{% highlight c# %}

	public partial class LoadOnDemand : System.Web.UI.Page
	{
		List<LoadData> tree1 = new List<LoadData>();
		protected void Page_Load(object sender, EventArgs e)
		{
			tree1.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
			tree1.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
			tree1.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
			tree1.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
			tree1.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
			tree1.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
			tree1.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
			tree1.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
			tree1.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
			tree1.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
			this.treeMultiSelect.Fields.DataSource = tree1;
		}
	} 
	
	public class LoadData
	{
		public int Id { get; set; }
		public int? Parent { get; set; }
		public string Text { get; set; }
		public bool? hasChild { get; set; }
		public bool? expanded { get; set; }
		public bool? ischecked { get; set; }
		public bool? selected { get; set; }
		public string spriteCss { get; set; }
	}

{% endhighlight %}

In the ASPX page, add TreeView element with following properties.

{% highlight html %}

	<ej:TreeView 
		ID="treeMultiSelect" 
		runat="server" 
		DataIdField="Id" 
		DataParentIdField="Parent" 
		DataTextField="Text" 
		AllowMultiSelection="true">
	</ej:TreeView>
	
{% endhighlight %}

## Select Nodes

To select more than one nodes of TreeView, you can use [selectedNodes](http://help.syncfusion.com/js/api/ejtreeview#members:selectednodes) property. It will select the TreeView nodes from the given indexes.

In the ASPX page, add TreeView element with following properties. We you can select the specific nodes in TreeView by using **selectedNodes** property.

{% highlight html %}

	<ej:TreeView 
		ID="treeMultiSelect" 
		runat="server" 
		DataIdField="Id" 
		DataParentIdField="Parent" 
		DataTextField="Text" 
		AllowMultiSelection="true">
	</ej:TreeView> 

{% endhighlight %}

{% highlight js %}

	$(function () {
        // create instance for TreeView
        var treeObj = $("#treeMultiSelect").data("ejTreeView");

        treeObj.option("selectedNodes", [0, 5, 6]); //select the TreeView nodes from the given indexes
    });
	
{% endhighlight %}

## Get Selected Nodes

To get the selected Nodes of TreeView, you can use [getSelectedNodes](http://help.syncfusion.com/js/api/ejtreeview#methods:getselectednodes) method. It returns the collections of TreeView selected nodes. You can use [getSelectedNodesIndex](https://help.syncfusion.com/api/js/ejtreeview#methods:getselectednodesindex) method to get the index positions of currently selected nodes.

In the ASPX page, add TreeView element with following properties. We you can get selected nodes from TreeView by using **getSelectedNodes** method.

{% highlight html %}

	<ej:TreeView 
		ID="treeMultiSelect" 
		runat="server" 
		DataIdField="Id" 
		DataParentIdField="Parent" 
		DataTextField="Text" 
		AllowMultiSelection="true">
	</ej:TreeView>

{% endhighlight %}

{% highlight js %}

	$(function () {
        // create instance for TreeView
        var treeObj = $("#treeMultiSelect").data("ejTreeView");

        treeObj.getSelectedNodes(); //returns the collections of TreeView selected nodes
    });
	
{% endhighlight %}

