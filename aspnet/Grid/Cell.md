---
layout: post
title: Cells with Grid widget for Syncfusion Essential ASP.NET
description: How to define the cell and its features
platform: aspnet
control: Grid
documentation: ug
--- 
# Cell

## Auto wrap 

Auto wrap enables the Grid to wrap cell content or header content to next line when the content exceeds the boundary of the cell width. To enable auto wrap, set `AllowTextWrap` property as `true`. 

We can specify the mode of auto wrap using `WrapMode` property of the `TextWrapSettings`. 

Three types of `WrapMode` are available and they are,
  
 1. Both
 2. Header
 3. Content 
 
N> 1. By default the `WrapMode` will be set as `Both`. 

N> 2. While using `TextWrapSettings` then it is must to set `AllowTextWrap` as `true`.
 
## Both

When `WrapMode` of `TextWrapSettings` property set as `Both` then the auto wrap will be enable for both grid content and header. 

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true"  AllowTextWrap="true">
      <TextWrapSettings WrapMode="Both" />
        <Columns>
                <ej:Column Field="OrderID"   Width="90" />
                <ej:Column Field="CustomerID" Width="100" />
                <ej:Column Field="EmployeeID" Width="100" />
                <ej:Column Field="Freight" Width="90"  />
                <ej:Column Field="ShipAddress" HeaderText="Ship Address"  Width="110" />
         </Columns>
       </ej:Grid>
     </asp:Content>
      
{% endhighlight  %}

{% highlight c# %}

    namespace WebSampleBrowser.Grid
    {
        public partial class _Default : Page
        {
        protected void Page_Load(object sender, EventArgs e)
            {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
      }
    }
    
{% endhighlight  %}

{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img1.png)

### Header

When `WrapMode` of `TextWrapSettings` property set as `Header` then the auto wrap will be enable only for grid header alone. 

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true"  AllowTextWrap="true">
      <TextWrapSettings WrapMode="Header" />
        <Columns>
                <ej:Column Field="OrderID"   Width="90" />
                <ej:Column Field="CustomerID" Width="100" />
                <ej:Column Field="EmployeeID" Width="100" />
                <ej:Column Field="Freight" Width="90"  />
                <ej:Column Field="ShipAddress" HeaderText="Ship Address"  Width="110" />
         </Columns>
     </ej:Grid>
     </asp:Content>
     
{% endhighlight  %}

{% highlight c# %}

    namespace WebSampleBrowser.Grid
    {
        public partial class _Default : Page
        {
        protected void Page_Load(object sender, EventArgs e)
            {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
      }
    }
    
{% endhighlight  %}

{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img1_1.png)

### Content

When `WrapMode` of `TextWrapSettings` property set as `Content` then the auto wrap will be enable only for grid content alone. 

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true"  AllowTextWrap="true">
      <TextWrapSettings WrapMode="Content" />
        <Columns>
                <ej:Column Field="OrderID"   Width="90" />
                <ej:Column Field="CustomerID" Width="100" />
                <ej:Column Field="EmployeeID" Width="100" />
                <ej:Column Field="Freight" Width="90"  />
                <ej:Column Field="ShipAddress" HeaderText="Ship Address"  Width="110" />
         </Columns>
     </ej:Grid>
     </asp:Content>
     
{% endhighlight  %}

{% highlight c# %}

    namespace WebSampleBrowser.Grid
    {
        public partial class _Default : Page
        {
        protected void Page_Load(object sender, EventArgs e)
            {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
      }
    }
    
{% endhighlight  %}

{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img1_2.png)

## Cell Merging

The Grid has options to merge the Grid cells based on the required conditions. This can be enabled by setting `AllowCellMerging` property as `true` and the merge conditions can be defined in `MergeCellInfo` event. In this event, you can get the column details and data of that particular row and column which is helpful in defining conditions. 

You can merge the rows and cells of grid, using `rowMerge`, `colMerge` and `merge` functions available in `MergeCellInfo` event's argument.

N> The following features are not supported with Cell Merging
N> 1. Normal Mode Editing
N> 2. Inline Mode Editing
N> 3. Inline TemplateForm Mode Editing

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" AllowCellMerging="true">
        <ClientSideEvents MergeCellInfo="mergeCellInfo" />
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipCountry" />
            <ej:Column Field="Freight" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
    <script type="text/javascript">
        function mergeCellInfo(args) {
            if (args.column.field == "EmployeeID" && args.rowData.OrderID == 10261)
                args.rowMerge(3);
            else if (args.column.field == "ShipCity" && args.rowData.OrderID == 10265)
                args.colMerge(3);
            else if (args.column.field == "ShipCity" && args.rowData.OrderID == 10268)
                args.merge(0, 3);
        }
    </script>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
         protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img2.png)


## Custom Attribute

You can add `Custom attribute` for particular column `td` element by using `CustomAttributes` property of the column.

Based on custom attribute you can customize the style and appearance of the `td` element for particular column or handling jQuery functionalities. 

You can use JsRender syntax in the template.For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link").

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="CustomerID" />
            <ej:Column Field="EmployeeID" HeaderText="Employee Name">
                <CustomAttribute>
                    <ej:KeyValue Key="employeeid" Value="5" />
                </CustomAttribute>
            </ej:Column>
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipCountry" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight css %}
    <style>
        .e-rowcell[employeeid = "5"] {
            color: red;
        }	
    </style>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 
The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img3.png)


## Displaying HTML content

This will helps you to show actual `HTML` value in grid content and header. To disable HTML code, set `disableHtmlEncode` property of `Columns` as true. 

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="CustomerID" HeaderText="<div>Customer ID</div>" disableHtmlEncode="true"/>
            <ej:Column Field="EmployeeID" HeaderText="<div>Employee ID</div>" disableHtmlEncode="false"/>
            <ej:Column Field="ShipCountry" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 
The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img4.png)

## Tooltip

When you move the cursor over the particular cell it provides an information about the corresponding cell value.

**Template**

HTML templates can be specified in the `Tooltip` property of the particular column cell as a string (HTML element) or ID of the template's HTML element.You can use JsRender syntax in the template. For more information about JsRender syntax, please refer [this link](http://www.jsviews.com/#jsrapi "this link"). 

N> It's a standard way to enclose the template within the `script` tag with `type` as "text/x-jsrender".
 
N> The `Tooltip` template must contain `value` property to bind the corresponding cell text in tooltip
 
The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="ShipCity" Tooltip= "#colTip"/>
            <ej:Column Field="Freight" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
<script type="text/template" id="colTip">
  {{"{{"}}:value {{}}}} 
</script>       
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
       protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img5.png)

## ClipMode

When the cell value contains a long text that is not fit into the grid column cell, the `ClipMode` property is used. By using the `ClipMode`, the cell value will be displayed with ellipsis or with clipped content when the text overflows inside a column cell.

N>  By default the `ClipMode` will be set as `Clip`. 


**List of types**
  
 1. Clip
 2. Ellipsis
 3. EllipsisWithTooltip 
 
### Clip

When the content overflows, the remaining content will be hidden in the particular cell

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
     <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipName" ClipMode="Clip"/> 
            <ej:Column Field="Freight" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
       protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img6.png)
 
### Ellipsis

Ellipsis will be displayed when the content overflows its column width. Here Tooltip will not be shown for corresponding columns.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
     <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipName" ClipMode="Ellipsis"/> 
            <ej:Column Field="Freight" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
       protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 


The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img7.png)

### Ellipsis With Tooltip

Ellipsis will be displayed when the content overflows its column width. Here tooltip will be shown only for the corresponding column cells that shows ellipsis.

N> If `ClipMode` is set as `EllipsisWithTooltip`, then `Tooltip` must be given.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
     <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipName" Tooltip="#colTip" ClipMode="EllipsisWithTooltip"/> 
            <ej:Column Field="Freight" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
<script type="text/template" id="colTip">
  {{"{{"}}:value {{}}}} 
</script>       
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
       protected void Page_Load(object sender, EventArgs e)
        {
            var data = new NorthWindDataContext().Orders.ToList();
            FlatGrid.DataSource = data;
            FlatGrid.DataBind();
        }
    }
}
{% endhighlight  %}
{% endtabs %} 
The following output is displayed as a result of the above code example.

![](Cell_images/Cell_img8.png)



