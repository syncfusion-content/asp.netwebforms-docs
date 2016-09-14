---
layout: post
title: TreeView with Multiple Drag and Drop option | TreeView | ASP.NET | Syncfusion
description: Specify multiple drag and drop option in TreeView and its settings
platform: aspnet
control: TreeView
documentation: UG
---


# Drag and Drop Multiple Nodes

TreeView supports to drag and drop multiple nodes by specifying [allowMultiSelection](http://help.syncfusion.com/js/api/ejtreeview#members:allowmultiselection) as true along with [allowDragAndDrop](https://help.syncfusion.com/js/api/ejtreeview#members:allowdraganddrop) as true. It allows you to drag and drop multiple nodes in TreeView.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.

{% highlight c# %}

	public partial class LoadOnDemand : System.Web.UI.Page
	{
		List<LoadData> treeData1 = new List<LoadData>();
		List<LoadData> treeData2 = new List<LoadData>();
		protected void Page_Load(object sender, EventArgs e)
		{
			treeData1.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1" });
			treeData1.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
			treeData1.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
			treeData1.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
			treeData1.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
			treeData1.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
			treeData1.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
			treeData1.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
			treeData1.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
			treeData1.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
			this.treeViewDrag.Fields.DataSource = treeData1;
			treeData2.Add(new LoadData { Id = 11, Parent = 0, Text = "Item 5" });
			treeData2.Add(new LoadData { Id = 12, Parent = 0, Text = "Item 6" });
			treeData2.Add(new LoadData { Id = 13, Parent = 0, Text = "Item 7" });
			treeData2.Add(new LoadData { Id = 14, Parent = 0, Text = "Item 4" });
			treeData2.Add(new LoadData { Id = 15, Parent = 11, Text = "Item 5.1" });
			treeData2.Add(new LoadData { Id = 16, Parent = 11, Text = "Item 5.2" });
			treeData2.Add(new LoadData { Id = 17, Parent = 11, Text = "Item 5.3" });
			treeData2.Add(new LoadData { Id = 18, Parent = 13, Text = "Item 7.1" });
			treeData2.Add(new LoadData { Id = 19, Parent = 13, Text = "Item 7.2" });
			treeData2.Add(new LoadData { Id = 10, Parent = 15, Text = "Item 5.1.1" });
			this.treeViewDrop.Fields.DataSource = treeData2;
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

In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source with that specify the multiple drag and drop settings.

{% highlight html %}

	<div style="float: left; width: 200px;">
		<ej:TreeView
			ID="treeViewDrag"
			runat="server"
			DataTextField="Text"
			DataIdField="Id"
			DataParentIdField="Parent"
			AllowDragAndDrop="true" 
			AllowMultiSelection="true">
		</ej:TreeView>
	</div>
	<div style="float: left; width: 200px;">
		<ej:TreeView
			ID="treeViewDrop"
			runat="server"
			DataTextField="Text"
			DataIdField="Id"
			DataParentIdField="Parent"
			AllowDragAndDrop="true" 
			AllowMultiSelection="true">
		</ej:TreeView>
	</div>
	
{% endhighlight %}

