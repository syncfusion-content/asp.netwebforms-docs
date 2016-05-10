---
title: State Persistence | TreeView | ASP.NET | Syncfusion
description: State Persistence option in TreeView
platform: aspnet
control: TreeView
documentation: UG
keywords: TreeView,  Syncfusion, ASP Web TreeView UG Doc, State Persistence
---

# State Persistence

TreeView state can be persisted by using ‘**EnablePersistence**’. In which user intractable model values only has been persisted in order to maintain performance.

The model values of below are maintained through id basis of tree node.

* selected
* checked
* expanded/ collapsed state

N>**In UL LI template state has been persisted by index.**

TreeView stores its model in local storage/ cookies of browser before page refreshes and reinitialized with their stored model after refresh.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
                treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                this.treeView.DataSource = treeData;
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
    
In the ASPX page, add TreeView element with following properties.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            EnablePersistence="true">
        </ej:TreeView>
        
    {% endhighlight %}
  
