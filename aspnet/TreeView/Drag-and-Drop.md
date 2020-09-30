---
layout: post
title: Drag and Drop option | ASP.NET TreeView | Syncfusion
description: Specify Drag and Drop option in TreeView and its settings
platform: aspnet
control: TreeView
documentation: UG
---

# Drag and drop 

To perform drag and drop operation in TreeView specify “**AllowDragAndDrop**” as true. It allows you to drag and drop node in all level of same TreeView.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            AllowDragAndDrop="true">
        </ej:TreeView>
        
    {% endhighlight %}
    
N>**TreeView provides much easier option to drop the dragged nodes at any levels by indicator lines with icons.**

## Position Indicators

TreeView provides much easier option to drop the dragged nodes at any levels by indicator lines with icons such as line, plus/ minus and restrict icons while dragging and dropping the nodes. It represents exact position where the node to be dropped as sibling or child.

<table>
<tr>
<td>
    {{'**Indicators**'| markdownify }}
</td>
<td>
    {{'**description**'| markdownify }}
</td>
</tr>
<tr>
<td>
Plus icon
</td>
<td>
represents the dragged node to be added as child of targeted node
</td>
</tr>
<tr>
<td>
Minus with restrict icon
</td>
<td>
represents the dragged node not to be dropped at the hovered region
</td>
</tr>
<tr>
<td>
In between icon
</td>
<td>
represents the dragged node to be dropped in between the nodes as siblings
</td>
</tr>
</table>

## Restriction

You can restrict the dragged nodes to be dropped at siblings or children’s level by using “**AllowDropSibling**” and ’‘**AllowDropChild’** property.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            AllowDragAndDrop="true"
            AllowDropSibling="true"
            AllowDropChild="false">
        </ej:TreeView>
        
    {% endhighlight %}
    
## Drag and drop between Trees

You can drag and drop tree nodes between two TreeView by setting “**AllowDragAndDrop**” as true along with “**AllowDragAndDropAcrossControl**” as true.

The [nodeDrag](https://help.syncfusion.com/api/js/ejtreeview#events:nodedrag), [nodeDragStart](https://help.syncfusion.com/api/js/ejtreeview#events:nodedragstart), [nodeDragStop](https://help.syncfusion.com/api/js/ejtreeview#events:nodedragstop) and 
[nodeDropped](https://help.syncfusion.com/api/js/ejtreeview#events:nodedropped) event occurs based on Treeview node drag and drop state. 

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData1 = new List<LoadData>();
            List<LoadData> treeData2 = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData1.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                treeData1.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                treeData1.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData1.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
                treeData1.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData1.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData1.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData1.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData1.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData1.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                this.treeViewDrag.DataSource = treeData1;
                treeData2.Add(new LoadData { Id = 11, Parent = 0, Text = "Item 5", Expanded = true });
                treeData2.Add(new LoadData { Id = 12, Parent = 0, Text = "Item 6" });
                treeData2.Add(new LoadData { Id = 13, Parent = 0, Text = "Item 7" });
                treeData2.Add(new LoadData { Id = 14, Parent = 0, Text = "Item 4" });
                treeData2.Add(new LoadData { Id = 15, Parent = 11, Text = "Item 5.1" });
                treeData2.Add(new LoadData { Id = 16, Parent = 11, Text = "Item 5.2" });
                treeData2.Add(new LoadData { Id = 17, Parent = 11, Text = "Item 5.3" });
                treeData2.Add(new LoadData { Id = 18, Parent = 13, Text = "Item 7.1" });
                treeData2.Add(new LoadData { Id = 19, Parent = 13, Text = "Item 7.2" });
                treeData2.Add(new LoadData { Id = 10, Parent = 15, Text = "Item 5.1.1" });
                this.treeViewDrop.DataSource = treeData2;
            }
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source with that specify the drag and drop settings.
    
    {% highlight html %}
    
        <div style="float: left; width: 200px;">
            <ej:TreeView
                ID="treeViewDrag"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                AllowDragAndDrop="true"
                AllowDropChild="true"
                AllowDropSibling="true"
                AllowDragAndDropAcrossControl="true">
            </ej:TreeView>
        </div>
        <div style="float: left; width: 200px;">
            <ej:TreeView
                ID="treeViewDrop"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                AllowDragAndDrop="true"
                AllowDropChild="true"
                AllowDropSibling="true"
                AllowDragAndDropAcrossControl="true">
            </ej:TreeView>
        </div>
        
    {% endhighlight %}
    
## Auto node structuring

You may not need to have two TreeView to be in same structured node while drag and drop the nodes between them. But after the node has been dropped, it should get structure of the TreeView node in which dropped. By default TreeView auto structure the node whenever you drop a node from different tree.
    
    {% highlight html %}
    
        <div style="float: left; width: 200px;">
            <ej:TreeView
                ID="treeViewDrag"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                AllowDragAndDrop="true"
                AllowDropChild="true"
                AllowDropSibling="true"
                AllowDragAndDropAcrossControl="true" 
                ShowCheckbox="true">
            </ej:TreeView>
        </div>
        <div style="float: left; width: 200px;">
            <ej:TreeView
                ID="treeViewDrop"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                AllowDragAndDrop="true"
                AllowDropChild="true"
                AllowDropSibling="true"
                AllowDragAndDropAcrossControl="true">
            </ej:TreeView>
        </div>
        
    {% endhighlight %}
    
N>**Auto node structure only applicable for well-structured node object.**



