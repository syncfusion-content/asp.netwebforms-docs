---
layout: post
title: TreeView with Full Row Selection option | TreeView | ASP.NET | Syncfusion
description: Specify full row selection option in TreeView and its settings
platform: aspnet
control: TreeView
documentation: UG
---


# Full Row Selection

The TreeView control provides the option to highlight a full row of tree view nodes. When **FullRowSelect** is set to **true**, selection highlights the entire width of the tree view and displays the tree node text instead of the width. It makes selection easier.

In the code behind page, create a data list which contains the details about tree nodes of TreeView.

{% highlight c# %}

[Serializable]
public class FullRowSelectDataSource
{
    public FullRowSelectDataSource(int _id, int _parentId, string _text, string _hasChild = "", string _expanded = "", string _selected = "")
    {
        this.ID = _id;
        this.ParentID = _parentId;
        this.Text = _text;
        this.HasChild = _hasChild;
        this.Expanded = _expanded;
        this.Selected = _selected;
    }
    public FullRowSelectDataSource() { }

    [Browsable(true)]
    public int ID { get; set; }

    [Browsable(true)]
    public int ParentID { get; set; }

    [Browsable(true)]
    public string Text { get; set; }

    [Browsable(true)]
    public string HasChild { get; set; }

    [Browsable(true)]
    public string Expanded { get; set; }

    [Browsable(true)]
    public string Selected { get; set; }

    public List<FullRowSelectDataSource> GetFullRowItems()
    {
        List<FullRowSelectDataSource> fullRowData = new List<FullRowSelectDataSource>();
        fullRowData.Add(new FullRowSelectDataSource(1, 0, "Discover Music", "true", "true"));
        fullRowData.Add(new FullRowSelectDataSource(2, 1, "Hot Singles", "", "", "true"));
        fullRowData.Add(new FullRowSelectDataSource(3, 1, "Rising Artists"));
        fullRowData.Add(new FullRowSelectDataSource(4, 1, "Live Music"));
        fullRowData.Add(new FullRowSelectDataSource(6, 1, "Best of 2013 So Far"));
        fullRowData.Add(new FullRowSelectDataSource(7, 0, "Sales and Events", "true", "true"));
        fullRowData.Add(new FullRowSelectDataSource(8, 7, "100 Albums - $5 Each"));
        fullRowData.Add(new FullRowSelectDataSource(9, 7, "Hip-Hop and R&B Sale"));
        fullRowData.Add(new FullRowSelectDataSource(10, 7, "CD Deals"));
        fullRowData.Add(new FullRowSelectDataSource(11, 0, "Categories", "true"));
        fullRowData.Add(new FullRowSelectDataSource(12, 11, "Songs"));
        fullRowData.Add(new FullRowSelectDataSource(13, 11, "Bestselling Albums"));
        fullRowData.Add(new FullRowSelectDataSource(14, 11, "New Releases"));
        fullRowData.Add(new FullRowSelectDataSource(15, 11, "Bestselling Songs"));
        fullRowData.Add(new FullRowSelectDataSource(16, 0, "MP3 Albums", "true"));
        fullRowData.Add(new FullRowSelectDataSource(17, 16, "Rock"));
        fullRowData.Add(new FullRowSelectDataSource(18, 16, "Gospel"));
        fullRowData.Add(new FullRowSelectDataSource(19, 16, "Latin Music"));
        fullRowData.Add(new FullRowSelectDataSource(20, 16, "Jazz"));
        fullRowData.Add(new FullRowSelectDataSource(21, 0, "More in Music", "true"));
        fullRowData.Add(new FullRowSelectDataSource(22, 21, "Music Trade-In"));
        fullRowData.Add(new FullRowSelectDataSource(23, 21, "Redeem a Gift Card"));
        fullRowData.Add(new FullRowSelectDataSource(24, 21, "Band T-Shirts"));
        fullRowData.Add(new FullRowSelectDataSource(25, 21, "Mobile MVC"));
        return fullRowData;
    }
}

{% endhighlight %}

In the ASPX page, add TreeView element with following properties.

{% highlight html %}

<ej:TreeView ID="fullRowTree" runat="server" DataSourceID="ObjectData" DataTextField="Text"
    DataIdField="ID" DataParentIdField="ParentID" DataHasChildField="HasChild"
    DataExpandedField="Expanded" DataSelectedField="Selected" FullRowSelect="true" >
</ej:TreeView>
<asp:ObjectDataSource ID="ObjectData" runat="server" TypeName="FullRowSelectDataSource"
    SelectMethod="GetFullRowItems"></asp:ObjectDataSource>

{% endhighlight %}

For more details about full row selection in TreeView, refer the sample [here](http://asp.syncfusion.com/demos/web/treeview/fullrowselection.aspx).

## Customization

You can customize the TreeView full row selection for template support by using **CssClass** property. Based on this custom class, you can customize the height of the highlighting TreeView node.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.

{% highlight c# %}

public partial class FullRowSelection : System.Web.UI.Page
{
    List<loadOnDemand> fullRowData = new List<loadOnDemand>();
    protected void Page_Load(object sender, EventArgs e)
    {
        fullRowData.Add(new loadOnDemand { id = 1, name = "Browsers", className = "browser", hasChild = true, expanded = true });
        fullRowData.Add(new loadOnDemand { id = 2, parent = 1, name = "Internet Explorer", className = "ie-browser", selected = true });
        fullRowData.Add(new loadOnDemand { id = 3, parent = 1, name = "Chrome", className = "chrome-browser" });
        fullRowData.Add(new loadOnDemand { id = 4, parent = 1, name = "Firefox", className = "firefox-browser" });
        fullRowData.Add(new loadOnDemand { id = 6, parent = 1, name = "Bitty", className = "bitty-browser" });
        fullRowData.Add(new loadOnDemand { id = 7, parent = 1, name = "Opera", className = "opera-browser" });

        this.fullRowTree.Fields.DataSource = fullRowData;

    }
}
public class loadOnDemand
{
    public int id { get; set; }
    public int? parent { get; set; }
    public string name { get; set; }
    public bool? hasChild { get; set; }
    public bool? expanded { get; set; }
    public bool? ischecked { get; set; }
    public bool? selected { get; set; }
    public string spriteCss { get; set; }
    public string className { get; set; }
}

{% endhighlight %}

In the ASPX page, add TreeView element with following properties.

{% highlight html %}

<ej:TreeView ID="fullRowTree" runat="server" DataTextField="name" DataIdField="id" 
    DataParentIdField="parent" DataHasChildField="hasChild" DataExpandedField="expanded" 
    DataSelectedField="selected" FullRowSelect="true" Template="#treeTemplate" CssClass="custom">
</ej:TreeView>

<script id="treeTemplate" type="text/x-jsrender">

    {{"{{"}}if !hasChild{{}}}}
    <span class="con-img {{"{{"}}>className{{}}}}"></span>
    {{"{{"}}/if{{}}}}
    {{"{{"}}>name{{}}}}

</script>
	
{% endhighlight %}

{% highlight css %}

<style>
    .custom .con-img {
        background-image: url("http://asp.syncfusion.com/demos/web/Content/images/toolbar/browserl.png");
        background-repeat: no-repeat;
        height: 32px;
        width: 32px;
        display: inline-block;
        overflow: hidden;
        background-repeat: no-repeat;
        text-align: center;
        vertical-align: middle;
    }
    
    .custom .e-li-active > .e-text-wrap .con-img {
        background-image: url("http://asp.syncfusion.com/demos/web/Content/images/toolbar/browserh.png");
    }
    
    .custom .e-li-hover > .e-text-wrap .con-img, .e-fullrow-wrap .e-li-focus > .e-text-wrap .con-img {
        background-image: url("http://asp.syncfusion.com/demos/web/Content/images/toolbar/browserl.png");
    }
    
    .custom .ie-browser {
        background-position: -84px 0px;
    }
    
    .custom .chrome-browser {
        background-position: -42px 0px;
    }
    
    .custom .firefox-browser {
        background-position: 0px 0px;
    }
    
    .custom .bitty-browser {
        background-position: -126px 0px;
    }
    
    .custom .opera-browser {
        background-position: -168px 0px;
    }
    
    /*customize the height of highlighting TreeView node*/
    .custom.e-fullrow-wrap .e-item ul .e-fullrow {
        margin-top: -36px;
        height: 36px;
    }

</style>

{% endhighlight %}

