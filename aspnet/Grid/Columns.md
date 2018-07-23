---
layout: post
title: Columns with Grid widget for Syncfusion Essential ASP.NET
description: How to define the columns and its features
platform: aspnet
control: Grid
documentation: ug
--- 
# Columns

Column definitions are used as the `DataSource` schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on the column definitions. The `Field` property of the `Columns` is necessary to map the datasource values in Grid columns.

N> 1. If the column with `Field` is not in the datasource, then the column values will be displayed as empty.
N> 2. If the `Field` name contains "dot" operator then it is considered as complex binding.

## Auto generation

The `Columns` are automatically generated when `Columns` declaration is empty or undefined while initializing the Grid. Also, all the columns which are in `DataSource` are bound as a Grid columns.

The following code example shows auto-generate columns behavior.

{% tabs %}
{% highlight html %}
  	<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
       <ej:Grid id="FlatGrid"  runat="server"  AllowPaging="true">
       </ej:Grid>
     </asp:Content>          
{% endhighlight  %}
{% highlight c# %}
   namespace WebSampleBrowser.Grid
   {
    public partial class _Default : Page
    {
        List<Orders> order = new List<Orders>();
        protected void Page_Load(object sender, EventArgs e)
        {
           BindDataSource();
		}
        private void BindDataSource()
          {
                int orderId = 10643;
                int empId = 0;
                for (int i = 1; i < 9; i++)
                {
                    order.Add(new Orders(orderId + 1, empId + 1,"Reims", 32.38, "Germany"));
                    order.Add(new Orders(orderId + 2, empId + 2,"Munster", 11.61, "Mexico"));
                    order.Add(new Orders(orderId + 3, empId + 3,"Rio de janerio" , 45.34,  "Mexico"));
                    order.Add(new Orders(orderId + 4, empId + 4,"Lyon",37.28,  "UK"));
                    order.Add(new Orders(orderId + 5, empId + 5,"Bern", 67.00,  "Sweden"));
                    order.Add(new Orders(orderId + 6, empId + 6,"Graz", 23.32,  "France"));
                    orderId += 6;
                    empId += 6;
                }
            this.FlatGrid.DataSource = order;
            this.FlatGrid.DataBind();
         }
        [Serializable]
        public class Orders
        {
            public Orders()
            {

            }
            public Orders(int orderId,  int empId, string shipCity,double freight,  string shipCountry)
            {
                this.OrderID = orderId;
                this.EmployeeID = empId;
                this.ShipCity = shipCity;
                this.ShipCountry = shipCountry;
                this.Freight = freight;
            }
            public int OrderID { get; set; }
            public int EmployeeID { get; set; }
            public string ShipCity { get; set; }
            public string ShipCountry { get; set; }
            public double Freight { get; set; }
        }
    }
}
{% endhighlight  %}
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Columns_images/Columns_img1.png)


### How to set isPrimaryKey for auto generated columns when editing is enabled:

Using `DataBound` event, you can set `IsPrimaryKey` value as `true` by two ways. The following code example demonstrates the above behavior.

1. If primary key "column index" is known then refer the following code example

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" >
       <ClientSideEvents Databound="dataBound" />
       <EditSettings AllowEditing="true"></EditSettings>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
     <script type="text/javascript">
          function dataBound(args) {
             var column = args.model.columns[0];
             //(or)
             var column = this.getColumnByIndex(0);
             column.isPrimaryKey = true;
             //Here columns method used to update the particular column
             this.columns(column, "update");
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

2. If primary key "column field name" is known then refer the following code example
{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" >
       <ClientSideEvents Databound="dataBound" />
        <EditSettings AllowEditing="true"></EditSettings>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
     <script type="text/javascript">
          function dataBound(args) {
              var column = this.getColumnByField("OrderID");
              column.isPrimaryKey = true;
              //Here columns method used to update the particular column
              this.columns(column, "update");
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

## Headers

### HeaderText

It represents the title for particular column. To enable header text, set `HeaderText` property of `Columns`. The following code example describes the above behavior.

N> If `HeaderText` is not defined then the `Field` name is considered as header text for that particular column. If both `Field` name and `HeaderText` are not defined then the column is rendered with "empty" header text.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" />
            <ej:Column Field="EmployeeID" HeaderText="Emp ID" />
            <ej:Column Field="Freight" HeaderText="Freight" />
            <ej:Column Field="ShipCountry" HeaderText="Country" />
            <ej:Column Field="ShipCity" HeaderText="City" />
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

![](Columns_images/Columns_img2.png)

### Header Text alignment

`Align` the header text of column header using `HeaderTextAlign` property of `Columns`. There are four possible ways to align header text, they are

1. Right
2. Left
3. Center
4. Justify

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" />
            <ej:Column Field="EmployeeID" HeaderText="Emp ID"  HeaderTextAlign = "Right" />
            <ej:Column Field="Freight" HeaderText="Freight"/>
            <ej:Column Field="ShipCountry" HeaderText="Country" HeaderTextAlign = "Center"/>
            <ej:Column Field="ShipCity" HeaderText="City"  HeaderTextAlign = "Right" />
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

![](Columns_images/Columns_img3.png)


### Header Template

The template design that applies on for the column header. To render template, set `HeaderTemplateID` property of the `Columns`.

You can use JsRender syntax in the template. For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link").

N> It's a standard way to enclose the `template` within the `script` tag with `type` as `text/x-jsrender`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" />
            <ej:Column Field="EmployeeID" HeaderText="Emp ID" HeaderTemplateID="#empTemplate" />
            <ej:Column Field="Freight" HeaderText="Freight" />
            <ej:Column Field="ShipCountry" HeaderText="Country" />
            <ej:Column Field="ShipCity" HeaderText="City" />
        </Columns>
    </ej:Grid>
</asp:Content>        
{% endhighlight  %}
{% highlight js %}
    <script type="text/template" id="empTemplate">
        Emp ID
       <span class="e-userlogin e-icon employee"></span>
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

![](Columns_images/Columns_img4.png)


## Text alignment

You can `Align` both content and header text of particular column using `TextAlign` property of `Columns`. There are four possible ways to align content and header text of column, they are 

1. Right
2. Left
3. Center
4. Justify

N> 1. The `TextAlign` property will affect both content and header text of the grid.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" TextAlign="Right" />
            <ej:Column Field="EmployeeID" TextAlign="Right" />
            <ej:Column Field="Freight" TextAlign="Right" />
            <ej:Column Field="ShipCountry" TextAlign="Center" />
            <ej:Column Field="ShipCity" TextAlign="Justify" />
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

![](Columns_images/Columns_img5.png)


## Format

`Format` is the process of customizing the particular column data with specified jQuery recognized globalize formats, such as currency, numeric, decimal, percentage or dates. The globalize format can be specified by using `Format` property of `Columns`.

The `Format` value should be wrapped within "{0:" and "}". (For ex: "{0:C3}"). The [data format](https://github.com/jquery/globalize/tree/v0.1.1#format "data format") strings are available for the Date and Number types.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="Freight" Format="{0:C2}" />
            <ej:Column Field="OrderDate"  Format="{0:dd/MM/yyyy}"/>
            <ej:Column Field="ShipCity"/>
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

![](Columns_images/Columns_img6.png)


## Width

You can specify the width for particular column by setting `Width` property of `Columns` as in pixel (ex: 100) or in percentage (ex: 40%).

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" Width="10%" />
            <ej:Column Field="EmployeeID" Width="15%" />
            <ej:Column Field="Freight" Width="100" />
            <ej:Column Field="ShipCity" Width="150" />
            <ej:Column Field="ShipCountry" Width="100" />
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

![](Columns_images/Columns_img7.png)


## Resizing


The `AllowResizing` property enables the grid to set the width to columns based on resizing the grid column manually.


### Resizing modes


`ResizeMode` property of `ResizeSettings` is used to change the resizing modes. It indicates whether to define mode of resizing.


<table>
<tr>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td class="name">Normal</td>
<td class="description">New column size will be adjusted by all other Columns</td>
</tr>
<tr>
<td class="name">NextColumn</td>
<td class="description">New column Size will be adjusted using next column.</td>
</tr>
<tr>
<td class="name">Control</td>
<td class="description">New column Size will be adjusted using entire control</td>
</tr>
</table>


The following code example describes the above behavior.


{% tabs %}
{% highlight html %}


<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
<ej:Grid ID="Grid" runat="server" ClientIDMode="Static" AllowPaging="true" AllowResizing="true"> 
        <ResizeSettings ResizeMode="NextColumn"></ResizeSettings>
        <Columns>
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="80"/>
            <ej:Column Field="ShipPostalCode" HeaderText="Ship Postal Code" Width="40"/>
            <ej:Column Field="ShipName" HeaderText="Ship Name" Width="40"/>
            <ej:Column Field="ShipAddress" HeaderText="Ship Address" Width="100" />
        </Columns>
        <ClientSideEvents TemplateRefresh="refresh" />
    </ej:Grid>
</asp:Content>


{% endhighlight  %}
{% highlight c# %}


namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
        List<Orders> order = new List<Orders>();
        protected void Page_Load(object sender, EventArgs e)
        {
            this.Grid.DataSource = order;
            this.Grid.DataBind();
        }
    }
}


{% endhighlight  %}
{% endtabs %} 


## Resize to fit 

The `AllowResizeToFit` property enable the Grid to set width to columns based on maximum width of the particular column's content to facilitate full visibility of data in all the grid rows. This automatic behavior is applicable only for the columns which does not have width specified. 

On columns where "width is defined", double click on the particular column header's resizer symbol to resize the column to show the whole text. For example, refer the "ShipCity" column in the below code snippet and output screen shot. 

The following code example describes the above behavior. 

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" AllowResizeToFit="true">
        <Columns>
            <ej:Column Field="OrderID" Width="100" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="Freight" Width="75" />
            <ej:Column Field="ShipCity" Width="50" />
            <ej:Column Field="ShipAddress"  />
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

![](Columns_images/Columns_img8.png)

## Reorder

Reordering can be done by drag and drop the particular column header from one index to another index within the Grid. Reordering can be enabled by setting `AllowReordering` property as `true`.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
</asp:Content>
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true"  AllowReordering="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="EmployeeID"  />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipCountry" />
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

![](Columns_images/Columns_img10.png)


## Visibility

You can hide particular column in Grid view by setting `Visible` property of it as `false`.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="OrderID" Visible="false" />
            <ej:Column Field="Freight" />
            <ej:Column Field="ShipCity" />
            <ej:Column Field="ShipCountry" />
         </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight %}
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

![](Columns_images/Columns_img11.png)


## Unbound Column

You can define the unbound columns in Grid by not defining `Field` property for that particular column. Value for these columns can be populated either manually using `QueryCellInfo` event or by using column `Template` or by column `Format` property.

N> Editing, grouping, filtering, sorting, summary and searching support are not available for unbound columns.

The following code example describes the above behavior. 

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <EditSettings AllowDeleting="True"></EditSettings>
        <Columns>
            <ej:Column Field="OrderID" IsPrimaryKey="true" />
            <ej:Column Field="CustomerID" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="Freight" />
            <ej:Column HeaderText="" Format="<a onclick = click(this) href=#>Delete</a>" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}	
    <script type="text/javascript">
        function click(e) {
            var obj = $("#MainContent_FlatGrid").data("ejGrid");
            obj.deleteRecord("OrderID", obj.getSelectedRecords()[0]);
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

![](Columns_images/Columns_img13.png)


## Column Template

HTML templates can be specified in the `Template` property of the particular column as a string (HTML element) or ID of the template's HTML element.

You can use JsRender syntax in the template. For more information about JsRender syntax, please refer [this link](http://www.jsviews.com/#jsrapi "this link"). 

For template manipulation using JavaScript, either you can use JsRender [helper](https://www.jsviews.com/#helpers) function or `TemplateRefresh` grid event. For more information on `TemplateRefresh` event, refer [this link](https://help.syncfusion.com/aspnet/grid/how-to/display-other-syncfusion-controls-in-grid-columns "this link").

N> If `Field` is not specified, you will not able to perform editing, grouping, filtering, sorting, search and summary functionalities in particular column.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <PageSettings PageSize="4"></PageSettings>
        <Columns>
            <ej:Column HeaderText="Photo" Template="<img style='width: 75px; height: 70px' src='/13.2.0.29/themes/web/images/employees/{{:EmployeeID}}.png' alt='{{:EmployeeID}}.png' />" TextAlign="Center" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="FirstName" />
            <ej:Column Field="LastName" />
            <ej:Column Field="Country" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}

{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
        List<Orders> order = new List<Orders>();
        protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }
        private void BindDataSource()
        {
            order.Add(new Orders(1, "Nancy", "Davolio", "USA"));
            order.Add(new Orders(2, "Andrew", "Fuller", "USA"));
            order.Add(new Orders(3, "Janet", "Leverling", "USA"));
            order.Add(new Orders(4, "Margaret", "Peacock", "USA"));
            order.Add(new Orders(5, "Steven", "Buchanan", "UK"));
            order.Add(new Orders(6, "Michael", "Suyama", "UK"));
            order.Add(new Orders(7, "Robert", "King", "UK"));
            order.Add(new Orders(8, "Laura", "Callahan","USA"));
            this.FlatGrid.DataSource = order;
            this.FlatGrid.DataBind();
        }
        [Serializable]
        public class Orders
        {
            public Orders()
            {

            }
            public Orders(int EmployeeId, string FirstName, string LastName, string Country)
            {
                this.EmployeeID = EmployeeId;
                this.FirstName = FirstName;
                this.LastName = LastName;
                this.Country = Country;
            }
            public int EmployeeID { get; set; }
            public string FirstName { get; set; }
            public string LastName { get; set; }
            public string Country { get; set; }
        }
    }
}
{% endhighlight  %}
{% endtabs %} 
The following output is displayed as a result of the above code example.

![](Columns_images/Columns_img14.png)


## Controlling Grid actions

You can control the Grid actions of a particular column by setting `AllowSorting`, `AllowGrouping`, `AllowFiltering`, `AllowResizing` and `AllowEditing` properties.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" AllowFiltering="true" AllowGrouping="true" AllowSorting="true" AllowResizing="true">
        <EditSettings AllowEditing="True"></EditSettings>
        <Columns>
            <ej:Column Field="OrderID" IsPrimaryKey="true" />
            <ej:Column Field="EmployeeID" AllowEditing="true" AllowGrouping="true" AllowFiltering="true" AllowSorting="true" AllowResizing="true" />
            <ej:Column Field="Freight" />
            <ej:Column Field="ShipCity" />
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

## Read only

To make a column as "read-only" then set `AllowEditing` property of `Columns` as `false`.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <EditSettings AllowEditing="True"></EditSettings>
        <Columns>
            <ej:Column Field="OrderID" IsPrimaryKey="true" />
            <ej:Column Field="EmployeeID" AllowEditing="false" />
            <ej:Column Field="Freight" />
            <ej:Column Field="ShipCity" />
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

![](Columns_images/Columns_img15.png)


## Expression Column

`Expression` column is possible only for `Template` column.

You can use JsRender syntax in the template.For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link"). 

N> This expression column is supported at read only mode.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <EditSettings AllowEditing="true"></EditSettings>
        <Columns>
            <ej:Column Field="FoodName" />
            <ej:Column Field="Protein" />
            <ej:Column Field="Fat" />
            <ej:Column Field="Carbohydrate" />
            <ej:Column HeaderText="Calories In Take" Template="<span>{{"{{"}}:Protein * 4  + Fat * 4 + Carbohydrate * 9 {{}}}}</span>" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
    public partial class _Default : Page
    {
        List<Orders> order = new List<Orders>();
        protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }
        private void BindDataSource()
        {
            order.Add(new Orders("CHEESE BURGER", 15, 15, 28));
            order.Add(new Orders("PIZZA", 15, 9, 39));
            order.Add(new Orders("CHICKEN NOODLE", 4, 2, 9));
            order.Add(new Orders("YOGURT", 10, 2, 43));
            order.Add(new Orders("BEEF SANDWICH", 22, 13, 34));
            order.Add(new Orders("CHICKEN BURGER", 15, 10, 25));
            this.FlatGrid.DataSource = order;
            this.FlatGrid.DataBind();
        }
        [Serializable]
        public class Orders
        {
            public Orders()
            {

            }
            public Orders(string name, int protein, int fat, int carbohydrate)
            {
                this.FoodName = name;
                this.Protein = protein;
                this.Fat = fat;
                this.Carbohydrate = carbohydrate;
            }
            public string FoodName { get; set; }
            public int Protein { get; set; }
            public int Fat { get; set; }
            public int Carbohydrate { get; set; }

        }
    }
}
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Columns_images/Columns_img16.png)

## Command Column

### Default action buttons

Using `Command` column, you can add CRUD action buttons as one of the Grid column, through `Type` property of `Commands`. The type property supports the below default `UnboundType` buttons.

1. Edit
2. Save
3. Delete
4. Cancel

Through `ButtonOptions` property of `Commands`, you can specify all the button options which are supported by Essential Studio ASP.NET `Button` control. 

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>
        <Columns>
            <ej:Column Field="OrderID" IsPrimaryKey="true" />
            <ej:Column Field="EmployeeID" />
            <ej:Column Field="Freight" />
            <ej:Column Field="ShipCountry" />
            <ej:Column HeaderText="Manage Records" Width="130">
                <Command>
                    <ej:Commands Type="edit">
                        <ButtonOptions Text="Edit"></ButtonOptions>
                    </ej:Commands>
                    <ej:Commands Type="delete">
                        <ButtonOptions Text="Delete"></ButtonOptions>
                    </ej:Commands>
                    <ej:Commands Type="save">
                        <ButtonOptions Text="Save"></ButtonOptions>
                    </ej:Commands>
                    <ej:Commands Type="cancel">
                        <ButtonOptions Text="Cancel"></ButtonOptions>
                    </ej:Commands>
                </Command>
            </ej:Column>
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

![](Columns_images/Columns_img17.png)


### Custom buttons

You can add custom button in the command column by specifying the `Type` property of `Commands` as "empty" or any other `string` which does not corresponds to default `UnboundType` buttons.

N> 1. In command column you can add only buttons.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>
        <Columns>
            <ej:Column Field="EmployeeID" />
            <ej:Column HeaderText="Employee Details" Width="130" TextAlign="Center">
                <Command>
                    <ej:Commands Type="detail">
                        <ButtonOptions Text="Details" Width="100" Click="onClick"></ButtonOptions>
                    </ej:Commands>
                </Command>
            </ej:Column>
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight js %}
    <script type="text/javascript">
        function onClick(args) {
            var grid = $("#MainContent_FlatGrid").ejGrid("instance");
            var index = this.element.closest("tr").index();
            var record = grid.getCurrentViewData()[index];
            alert("Record Details: " + JSON.stringify(record));
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

![](Columns_images/Columns_img18.png)

## Column Chooser

Column chooser contains the list of all the columns which are defined in the `Columns` property. Using this you can control the visibility of columns in Grid. You can prevent to show the particular column name in column chooser by setting `ShowInColumnChooser` property of `Columns` as `false`. 

Column Chooser would be shown in the top right corner of Grid. To enable column chooser, set `ShowColumnChooser` property as `true`. 

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" ShowColumnChooser="true">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" />
            <ej:Column Field="EmployeeID" HeaderText="Employee Name" ShowInColumnChooser="false" />
            <ej:Column Field="Freight" HeaderText="Freight" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" />
            <ej:Column Field="ShipCountry" HeaderText="Ship Country" />
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

![](Columns_images/Columns_img19.png)


## Foreign Key Column

Lookup data source can be bound to `DataSource` property of `Columns`. Data `Field` and `Text` can be set using `ForeignKeyField` and `ForeignKeyValue` property of `Columns`.

In the `DataSource` property, we can bound local and remote data. 

I> For foreign key column the sorting and grouping is based on `ForeignKeyField` instead of `ForeignKeyValue`. You can refer [Foreign Key Adaptor](https://help.syncfusion.com/aspnet/grid/data-adaptors#foreign-key-adaptor) to sort and group the foreign key column based on `ForeignKeyValue`.

N> In remote data, server should be configured to perform select and filter operations since the Grid will try to fetch required columns using select operation and required data using filter operation.

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
	  <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" />
            <ej:Column Field="EmployeeID" HeaderText="Employee Name" ForeignKeyField="EmployeeID"
                ForeignKeyValue="FirstName" TextAlign="Left" />
            <ej:Column Field="Freight" HeaderText="Freight" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" />
            <ej:Column Field="ShipCountry" HeaderText="Ship Country" />
        </Columns>
    </ej:Grid>
</asp:Content>
{% endhighlight  %}
{% highlight c# %}
namespace WebSampleBrowser.Grid
{
 public partial class _Default : Page
    {
        List<Orders> order = new List<Orders>();
        List<Employee> employee = new List<Employee>();
        protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }

        private void BindDataSource()
        {
            int code = 10000;
            for (int i = 1; i < 10; i++)
            {
                order.Add(new Orders(code + 1, "ALFKI", i + 2, 32.38, "Berlin", "Germany"));
                order.Add(new Orders(code + 2, "ANATR", i + 1, 11.61, "Madrid", "Spain"));
                order.Add(new Orders(code + 3, "ANTON", i + 4, 4.36, "Cholchester", "UK"));
                order.Add(new Orders(code + 4, "BLONP", i + 1, 52.3, "Marseille", "France"));
                order.Add(new Orders(code + 5, "BOLID", i + 3, 60.34, "Tsawassen", "Canada"));
                code += 3;
            }
            this.FlatGrid.DataSource = order;
            this.FlatGrid.DataBind();

            employee.Add(new Employee(4, "Michael"));
            employee.Add(new Employee(2, "Anne"));
            employee.Add(new Employee(3, "Janet"));
            employee.Add(new Employee(4, "Andrew"));
            employee.Add(new Employee(5, "Margaret"));
            employee.Add(new Employee(6, "Nancy"));
            employee.Add(new Employee(7, "Robert"));
            employee.Add(new Employee(8, "Laura"));
            employee.Add(new Employee(9, "Steven"));
            employee.Add(new Employee(10, "James"));
            employee.Add(new Employee(11, "Smith"));
            employee.Add(new Employee(12, "Johnson"));
            employee.Add(new Employee(13, "George"));

            var index = this.FlatGrid.Columns.FindIndex(col => col.Field == "EmployeeID");
            this.FlatGrid.Columns.ElementAt(index).DataSource = employee;
                 //(or)
            this.FlatGrid.Columns.ElementAt(index).DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Employees/";
        }

        [Serializable]
        public class Orders
        {
            public Orders()
            {

            }
            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, string ShipCity, string ShipCountry)
            {
                this.OrderID = OrderId;
                this.CustomerID = CustomerId;
                this.EmployeeID = EmployeeId;
                this.Freight = Freight;
                this.ShipCity = ShipCity;
                this.ShipCountry = ShipCountry;
            }
            public long OrderID { get; set; }
            public string CustomerID { get; set; }
            public int EmployeeID { get; set; }
            public double Freight { get; set; }
            public string ShipCity { get; set; }
            public string ShipCountry { get; set; }
        }
        [Serializable]
        public class Employee
        {
            public Employee()
            {

            }
            public Employee(int EmployeeId, string FirstName)
            {
                this.EmployeeID = EmployeeId;
                this.FirstName = FirstName;
            }
            public int EmployeeID { get; set; }
            public string FirstName { get; set; }
        }
    }
}
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![](Columns_images/Columns_img20.png)

## Customize column

You can `Customize` the header and content of the particular column by `CssClass` property of the column.

The following code example describes the above behavior.

{% tabs %}
{% highlight css %}
    <style>
        .customizes.e-headercell {
            background-color: #2382c3;
            color: white;
            font-family: 'Bell MT';
            font-size: 20px;
        }
         .customizes.e-rowcell {
            background-color: #ecedee;
            font-family: 'Bell MT';
            color: red;
            font-size: 20px;
        }
    </style>
{% endhighlight  %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="CustomerID" />
            <ej:Column Field="EmployeeID" CssClass="customizes" />
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

![](Columns_images/Columns_img23.png)


## Type

Used to define the type of the particular column data. If the `Type` property of `Columns` is not specified then its type is automatically defined based on the first row data of that column.

N> The `Type` is needed for filtering feature when first row of the data is "null" or "empty".

The available column data type is tabulated as follows.

<table>
<tr>
<th>
Type</th><th>
Description</th>
</tr>
<tr>
<td>
string</td><td>
Gets or sets the type of the column value as string </td>
</tr>
<tr>
<td>
number</td><td>
Gets or sets the type of the column value as number</td>
</tr>
<tr>
<td>
date</td><td>
Gets or sets the type of the column value as date</td>
</tr>
<tr>
<td>
datetime</td><td>
Gets or sets the type of the column value as datetime</td>
</tr>
<tr>
<td>
boolean</td><td>
Gets or sets the type of the column value as true or false </td>
</tr>
<tr>
<td>
guid</td><td>
Gets or sets the type of the column value as guid</td>
</tr>
<tr>
<td>
checkbox </td><td>
Gets or sets the type of the column value as checkbox for row selection </td>
</tr>
</table>

The following code example describes the above behavior.

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true">
        <Columns>
            <ej:Column Field="OrderID" />
            <ej:Column Field="CustomerID" Type="string" />
            <ej:Column Field="EmployeeID" Type="number" />
            <ej:Column Field="Freight" />
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

![](Columns_images/Columns_img24.png)

## Column Layout

You can set the Grid's columns layout based on either Grid width or its columns width using `ColumnLayout` property of Grid. There are two ways to set the column layout, they are 

1. Auto
2. Fixed

{% tabs %}
{% highlight html %}
<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" ColumnLayout="Fixed">
        <Columns>
            <ej:Column Field="OrderID" Width="80" />
            <ej:Column Field="EmployeeID" Width="80" />
            <ej:Column Field="ShipCity" Width="90" />
            <ej:Column Field="ShipName" Width="110" />
            <ej:Column Field="ShipCountry" Width="100" />
            <ej:Column Field="Freight" Width="80" />
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

![](columns_images/columns_img25.png)

