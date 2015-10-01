---
layout: post
title: Load on Demand | TreeView | ASP.NET | Syncfusion
description: load on demand
platform: aspnet
control: TreeView
documentation: ug
---

# Load on Demand

Load on Demand option is useful when the full content of the TreeView is too large to be loaded completely, up front. The mechanism lets the nodes load their child nodes as you expand the parent by clicking the expand icon. While clicking on the parent node it first loads their particular child nodes and then loads the first level of nodes.

This feature is used reduce the loading time of the large number nodes in TreeView. For example, when you are using the TreeView with 10,000 nodes or greater, it takes a long time to load their child nodes. In this case, Load on Demand is used to load the particular part of child nodes when you click their parent node. Hence it reduces the loading time of TreeView.

To enable Load on demand, set the appropriate value for the LoadOnDemand property.

The following steps explain how to enable the LoadOnDemand property for TreeView.

In the ASPX page, add an element to configure TreeView.


{% highlight html %}

<%--In the Design page, assign the values for DataTextField, DataIdField, DataParentIdField, DataHasChildField--%>

<ej:TreeView ID="treeview" runat="server" DataTextField="Text" DataIdField="ID" DataParentIdField="ParentID" DataHasChildField="HasChild" LoadOnDemand="true">

</ej:TreeView>

{% endhighlight %}


{% highlight c# %}

// Define local DataSource elements by using the ID,parentID ,Text and HasChild fields in code behind and map the list data to DataSource property.

public partial class LoadOnDemand : System.Web.UI.Page

{

    protected void Page_Load(object sender, EventArgs e)

    {

        this.treeview.DataSource = new TreeOnDemandDataSource().GetTreeItems().ToList();

    }

}

public class TreeOnDemandDataSource

{

    public TreeOnDemandDataSource(int _id, int _parentid, string _text, string _hasChild)

    {

        this.ID = _id;

        this.ParentID = _parentid;

        this.Text = _text;

        this.HasChild = _hasChild;

    }

    public TreeOnDemandDataSource() { }

    public int ID

    {

        get;

        set;

    }

    public int ParentID

    {

        get;

        set;

    }

    public string Text

    {

        get;

        set;

    }

    public string HasChild

    {
        get;

        set;

    }

    public List<TreeOnDemandDataSource> GetTreeItems()

    {

        List<TreeOnDemandDataSource> data = new List<TreeOnDemandDataSource>();

        data.Add(new TreeOnDemandDataSource(1, 0, "Favorites", "true"));

        data.Add(new TreeOnDemandDataSource(2, 1, "Desktop", ""));

        data.Add(new TreeOnDemandDataSource(3, 1, "Downloads", ""));

        data.Add(new TreeOnDemandDataSource(4, 1, "Recent places", ""));

        data.Add(new TreeOnDemandDataSource(5, 0, "libraries", "true"));

        data.Add(new TreeOnDemandDataSource(6, 5, "Documents", "true"));

        data.Add(new TreeOnDemandDataSource(7, 6, "My Documents", ""));

        data.Add(new TreeOnDemandDataSource(8, 6, "Public Documents", ""));

        data.Add(new TreeOnDemandDataSource(9, 5, "Pictures", "true"));

        data.Add(new TreeOnDemandDataSource(10, 9, "My Pictures", ""));

        data.Add(new TreeOnDemandDataSource(11, 9, "Public Pictures", ""));

        data.Add(new TreeOnDemandDataSource(12, 5, "Music", "true"));

        data.Add(new TreeOnDemandDataSource(13, 9, "My Music", ""));

        data.Add(new TreeOnDemandDataSource(14, 9, "Public Music", ""));

        data.Add(new TreeOnDemandDataSource(15, 5, "Subversion", ""));

        data.Add(new TreeOnDemandDataSource(16, 0, "Computer", "true"));

        data.Add(new TreeOnDemandDataSource(17, 16, "Folder(C)", ""));

        data.Add(new TreeOnDemandDataSource(18, 16, "Folder(D)", ""));

        data.Add(new TreeOnDemandDataSource(19, 16, "Folder(F)", ""));

        return data;

    }
}

{% endhighlight %}

![](Load-on-Demand_images/Load-on-Demand_img1.png)