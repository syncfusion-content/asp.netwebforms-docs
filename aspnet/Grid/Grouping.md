---
layout: post
title: Grouping with Grid widget for Syncfusion Essential ASP
description: How to enable grouping and its functionalities
platform: aspnet
control: Grid
documentation: ug
---
# Grouping

The Grid control has options to group the records based on the required column. When grouping is applied, grouped records are organized into a hierarchical structure to facilitate easier expand and collapse of records. To enable grouping, set `AllowGrouping` property as `true`.

Columns can be grouped by simply dragging the column header and drop on the group drop area or simply click the group button which is displayed in the column. By default, sorting is done while grouping the column.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
    
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>             
           </ej:Grid>
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img1.png)


## Initial Grouping

While initializing the grid itself, there is an option to group the column and display it in a hierarchical structure. To enable initial grouping, set array of column's `Field` name to be grouped in `GroupedColumns` property  of `GroupSettings`.

The following code example describes the above behavior.
            
{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <GroupSettings  GroupedColumns="ShipCountry"></GroupSettings>
           <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
                      
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img2.png)


## Multi-Column Grouping

Group multiple columns by simply drag and drop the columns one by one from column header into group drop area.

The following code example describes the above behavior.

           
{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <GroupSettings  GroupedColumns="ShipCountry,CustomerID"></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
      
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img3.png)


## Group Buttons

To do grouping easily without doing drag and drop column header by setting `ShowToggleButton` property of `GroupSettings` as `true`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true" AllowPaging="true" >
           <GroupSettings  ShowToggleButton="true" ></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
              
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  


The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img4.png)


## Hide Ungroup Button

Hide ungroup button from grouped columns which is in the group drop area by setting the `ShowUngroupButton` property of `GroupSettings` as `false`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true" AllowSorting="true" AllowPaging="true" >
           <GroupSettings  ShowUngroupButton="false"  ></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
      
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img5.png)


## Hide Grouped Column

While grouping a particular column, there is an option to hide the grouped columns from grid. To enable hide grouped column option, set `ShowGroupedColumn` property of `GroupSettings` as `false`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <GroupSettings ShowGroupedColumn="false" ></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
      
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img6.png)


## AutoSize Drop Area

Drag any column header and move it to the group drop area, then its portion expands smoothly. Stop this animation by setting `EnableDropAreaAutoSizing` property of `GroupSettings` as `false`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <GroupSettings EnableDropAreaAutoSizing="false" ></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>   
      
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

## Hide Drop Area 

To avoid ungrouping or further grouping of a column after an initial column grouping by setting `ShowDropArea` property of `GroupSettings` as `false`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
     
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true" AllowPaging="true" >
           <GroupSettings ShowDropArea="false" GroupedColumns="ShipCountry" ></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>         
       
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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img8.png)


## Group Caption Format/Group Caption Template

Using `CaptionFormat` property of `GroupSettings` you can render any type of JsRender templates or customizing the group caption text. 

You can use JsRender syntax in the template.For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link").

N>  1. It's a standard way to enclose the `template` within the `script` tag with `type` as "text/x-jsrender". 
N>  2. Using locale property of `GroupCaptionFormat`, you can only customize the default group caption text.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}
           
           <ej:Grid ID="FlatGrid" runat="server" AllowGrouping="true"  AllowPaging="true" >
           <GroupSettings CaptionFormat="#template" ></GroupSettings>
             <Columns>
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"  />
                <ej:Column Field="ShipCountry" />
                <ej:Column Field="Freight" />
           </Columns>         
           </ej:Grid>        
         
{% endhighlight  %}
            
{% highlight js %}            
     
     <script id="template" type="text/x-jsrender">
                "{{"{{"}}:field{{}}}}-"{{"{{"}}:key{{}}}}
                  <button id="btn" class="btn">Collapse</button>
     </script>
     <script>
             function complete(args) {
                 $(".btn").ejButton({
                 click: "btnClick"
                });
             }
             function btnClick(args) {
                 var gridObj = $("#FlatGrid").data("ejGrid");
                 gridObj.expandCollapse(this.element.parent().prev());
                 $("#btn").ejButton("model.text", args.model.text == "Collapse" ? "Expand" : "Collapse");
             }
    </script>    

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
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}
    
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img9.png)


![](Grouping_images/Grouping_img10.png)

## Handling grouped records count in server-side    

When binding remote data to grid with on-demand data loading, only current page data knowledge is available to grid and so grouped records count would be shown based on current Page only. 

This can be rectified when binding data to grid using [WebMethodAdaptor](https://help.syncfusion.com/aspnet/grid/data-adaptors#webmethod-adaptor) of DataManager. The grouped column values should be passed into the `groupDs` property of return object from server-side along with datasource and count.

The following code example describes the above behavior.

{% tabs %}
 
{% highlight razor %}

<ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" AllowGrouping="true" AllowSorting="true">
            <DataManager URL="_Default.aspx/UrlDataSource" Adaptor="WebMethodAdaptor" />
            <GroupSettings  GroupedColumns="EmployeeID"></GroupSettings>
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75"/>
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />
                <ej:Column Field="OrderDate" HeaderText="Order Date" TextAlign="Right" Width="80" Format="{0:MM/dd/yyyy}">
                </ej:Column>
            </Columns>
        </ej:Grid>

{% endhighlight  %}

{% highlight c# %}

    namespace WebSampleBrowser.Grid
        {
            public partial class _Default : Page
              { 
                List<Orders> order = new List<Orders>();

              [WebMethod]
              [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
              public static object UrlDataSource(DataManager value)
              {
                IEnumerable data = BindDataSource();
                DataOperations ds = new DataOperations();
                IEnumerable GroupDs = new List<object>(); 
                var count = data.AsQueryable().Count();

                List<string> str = new List<string>();
                if (value.Group != null)
                    GroupDs = ds.PerformSelect(data, str); // Grouped records

                if (value.Sorted != null && value.Sorted.Count > 0) //Sorting
                {
                    data = ds.PerformSorting(data, value.Sorted);
                }

                data = ds.PerformSkip(data, value.Skip);    //Paging
                data = ds.PerformTake(data, value.Take);

                return new { result = data, count = count, groupDs = GroupDs };
              }
                 private void BindDataSource()
                  {   
                     int code = 10000;
                     for (int i = 1; i < 10; i++)
                     {
                      order.Add(new Orders(code + 1, "ALFKI", i + 0, "France",34.3 * i));
                      order.Add(new Orders(code + 2, "ANATR", i + 2, "Germany",35.3 * i));
                      order.Add(new Orders(code + 3, "ANTON", i + 1, "Brazil" ,325.3 * i));
                      order.Add(new Orders(code + 4, "BLONP", i + 3, "Italy",435.3 * i, ));
                      order.Add(new Orders(code + 5, "BOLID", i + 4, "Mexico",46.3 * i));
                      code += 5;
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
                     public Orders(long OrderId, int EmployeeId, string CustomerId, string ShipCountry,double Freight)
                      {
                        this.OrderID = OrderId;
                        this.EmployeeID = EmployeeId;
                        this.CustomerID = CustomerId;
                        this.Freight = Freight;
                        this.ShipCountry = ShipCountry;
                      }
                     public long OrderID { get; set; }
                     public int EmployeeID { get; set; }
                     public string CustomerID { get; set; }
                     public string ShipCountry { get; set; }
                     public double Freight { get; set; }
                   }
              }
        } 
{% endhighlight  %}   
{% endtabs %}  

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img11.png)