---
layout: post
title: Scrolling with Grid widget for Syncfusion Essential ASP
description: This section explains about the scrolling and its functionalities like Frozen Rows and Columns, Touch Scroll, Virtual Scroll and the types of Virtual Scroll.
platform: aspnet
control: Grid
documentation: ug
---
# Enable Scrolling in Grid

Scrolling can be enabled by setting `AllowScrolling`  as `true`. The height and width can be set to grid by using the properties  `Height` and `Width` property of  `ScrollSettings`. 

 N> If `Width`  and `Height`  is not defined in the `ScrollSettings`  property then the horizontal and vertical scrollbar is enabled, only when the grid width exceeds the browser width.

The height and width can be set in percentage and pixel. The default value for `Height`  and `Width`  in `ScrollSettings`  is 0 and `auto` respectively.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

     <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
       <ScrollSettings Width="400" Height="300" />        
        <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>
                <ej:Column Field="ShipAddress "/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress = shipAddress
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![Scrolling](Scrolling_images/Scrolling_img1.png)

## Set Width and Height in pixel 

To specify the `Width` and `Height` property of  `ScrollSettings` in pixel, by set the pixel value as integer. 

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

     <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
       <ScrollSettings Width="500" Height="300" />         
        <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipAddress"/> 
                <ej:Column Field="ShipCountry"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![In pixel](Scrolling_images/Scrolling_img2.png)

## Set Width and Height in percentage

To specify the `Width` and `Height` property of  `ScrollSettings`  in percentage, by set the percentage value as string.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

    <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
       <ScrollSettings Width="70%" Height="5%" />         
        <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>
                <ej:Column Field="ShipAddress "/>                
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress = shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![In percentage](Scrolling_images/Scrolling_img3.png)

## Set Width as auto

Specify `Width`  property of `ScrollSettings`  as auto, then the scrollbar is rendered only when the grid width exceeds the browser window width.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

     <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
       <ScrollSettings Width="auto" Height="300" />        
        <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>
                <ej:Column Field="ShipAddress "/> 
                <ej:Column Field="ShipAddress"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![Auto Width](Scrolling_images/Scrolling_img4.png)

## Frozen Columns

Specify `FrozenColumns`  property of `ScrollSettings`  to freeze the columns(upto the specified frozenColumns value) at the time of scrolling. Horizontal scrollbar must be enabling while specifying `FrozenColumns`  then only you can scroll and see the remaining columns with freeze pane.

N> `AllowScrolling`  must be `true` while specifying `FrozenColumns` .

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

     <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" FrozenColumns="2" />   
             <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>
                <ej:Column Field="ShipAddress"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![Frozen Columns](Scrolling_images/Scrolling_img5.png)


### Freeze particular columns:

To freeze selected columns in grid at the time of scrolling, by set `IsFrozen`  property of columns as `true`. `IsFrozen`  columns are rendered first in the grid even the columns index is different while declaring the `Columns` .

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

     <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" FrozenColumns="2" />   
             <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID"/>
                <ej:Column Field="Freight" IsFrozen="true"/>
                <ej:Column Field="OrderDate" Format("{0:dd/MM/yyyy}")/>
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry" IsFrozen="true", Width="100"/>
                <ej:Column Field="ShipAddress"/>                 
                <ej:Column Field="ShipPostalCode"/>                
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", 32.38, "07/04/1996", "France", "59 rue de l'Abbaye", 51100));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", 11.61, "07/05/1996", "Brazil", "Luisenstr. 48", 44087));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", 45.34, "07/09/1996", "France", "2, rue du Commerce", 05454-876));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", 37.28, "07/11/1996", "Germany", "Rua do Paço, 67", 69004));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", 67.00, "07/15/1996", "Germany", "Hauptstr. 31", 8010));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", 23.32, "07/16/1996", "USA", "Starenweg 5", 1204));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, double freight,DateTime orderDate,string shipCity, string shipCountry,string shipAddress,int shipPostalCode)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.Freight = freight;
                this.OrderDate = orderDate;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;                
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public double Freight { get; set; }
             public DateTime OrderDate { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }             
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![Frozen Column](Scrolling_images/Scrolling_img6.png)


### Frozen Columns alert Messages:

1. If `AllowScrolling`  is false while using `FrozenColumns`  then "Enable `AllowScrolling`  while using frozen Columns" alert message is thrown.
2. If `FrozenColumns`  is specified out of the grid column view then "Frozen columns should be in grid view area" alert message is thrown.
3. Frozen Rows and Columns are not supported the following features
 Grouping
 Row Template
 Detail Template
 Hierarchy Grid 
 Batch Editing
 Virtual Scrolling

If any one of the above feature is enabled along with Frozen Rows and Columns, then "Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template, Hierarchy Grid and Batch Editing" alert message is thrown.

## Frozen Rows

Specify `FrozenRows`  property of `ScrollSettings`  to freeze rows(upto the specified FrozenRows value) at the time of scrolling. Vertical scrollbar must be enabling while specifying `FrozenRows`  then only you can scroll and see the remaining rows with freeze pane.

N> `AllowScrolling`  must be `true` while specifying `FrozenRows` .

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

      <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" FrozenRows="4" /> 
          <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID" />
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>  
                <ej:Column Field="ShipAddress"/>            
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

The following output is displayed as a result of the above code example.

![Frozen Rows](Scrolling_images/Scrolling_img7.png)


## Touch scroll

In touch  supported devices you can scroll and show the content by swipe left, right, top and bottom. Disable touch scroll by setting `EnableTouchScroll`  property of `ScrollSettings`  as `false`.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

      <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
          <ScrollSettings Width="550" Height="300" EnableTouchScroll="false" /> 
          <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID" />
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>
                <ej:Column Field="ShipAddress"/>                
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %} 

## Virtual Scrolling

The virtual scrolling support allows you to load data that you require (load data based on page size) without buffering the entire huge database. To enable virtual scrolling by setting `AllowVirtualScrolling`  property of `ScrollSettings`  as `true`. 

We also have an enhanced virtual scrolling feature with an improvised virtual scrolling performance. To enable improvised virtual scrolling feature by setting `EnableVirtualization` property of `ScrollSettings` as true and it doesn't requires `AllowVirtualScrolling` to enabled. It allows you to load the grid with data while scrolling. In order to enable this, you need to enable `EnableVirtualization` property of the `ScrollSettings`. Some of the relevant functionalities of this are,

1.	White space will not be appeared in the Grid. 
2.	Improved page rendering performance. 
3.  It can render nearly 500 thousand records.

It supports two mode of virtualization. They are,

1. Normal Mode
2. Infinite or Continuous Mode

N> Enhanced Virtual Scrolling supports only Normal mode
N> The following features are not supported by virtual scrolling 
N> 1. Grouping
N> 2. Frozen Rows 
N> 3. Cell merging 
N> 4. Detail template 
N> 5. Hierarchy
N> 6. Editing

### Normal Mode:

It allows you to load the grid with data while scrolling. This can be achieved by setting `VirtualScrollMode`  as `Normal`.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

      <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" AllowVirtualScrolling="true" VirtualScrollMode="Normal" /> 
          <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID" />
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the above code example.

![Normal Mode](Scrolling_images/Scrolling_img8.png)

#### Enhanced Virtual Scrolling:

In order to enable this, you need to set the `EnableVirtualization` property of the `ScrollSettings` as true. 

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

      <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" EnableVirtualization="true" /> 
          <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID" />
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the above code example.

![Enhanced VirtualScroll](Scrolling_images/Scrolling_img10.png)


### Infinite or Continuous Mode:

In Infinite or Continuous mode, the data is loaded in grid when the scrollbar reaches the end.  You can enable the continuous mode by setting the `VirtualScrollMode`  property as `Continuous`.

The following code example describes the above behavior.

{% tabs %} 
{% highlight html %}

      <ej:Grid ID="OrdersGrid" runat="server" AllowScrolling="true">
        <ScrollSettings Width="550" Height="300" AllowVirtualScrolling="true" VirtualScrollMode="Continuous" /> 
          <Columns>                
                <ej:Column Field="OrderID" />
                <ej:Column Field="EmployeeID" />
                <ej:Column Field="CustomerID" />
                <ej:Column Field="ShipCity"/> 
                <ej:Column Field="ShipCountry"/> 
                <ej:Column Field="ShipAddress"/>               
                <ej:Column Field="ShipPostalCode"/>
                <ej:Column Field="Freight"/>
            </Columns>
        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}
		
     namespace MVCSampleBrowser.Grid
     {
       public partial class Scrolling : System.Web.UI.Page
        {
         List<Orders> order = new List<Orders>();
         protected void Page_Load(object sender, EventArgs e)
         {
            BindDataSource();
         }
         private void BindDataSource()
          {
            int orderId = 10000;
            int empId = 0;
            for (int i = 0; i < 9; i++)
              {
                order.Add(new Orders(orderId + 1, empId + 1, "VINET", "Reims", "France", "59 rue de l'Abbaye", 51100, 32.38));
                order.Add(new Orders(orderId + 2, empId + 2, "TRADH", "Münster", "Brazil", "Luisenstr. 48", 44087, 11.61));
                order.Add(new Orders(orderId + 3, empId + 3, "VICTE", "Rio de Janeiro", "France", "2, rue du Commerce", 05454-876, 45.34));
                order.Add(new Orders(orderId + 4, empId + 4, "FRANK", "Lyon", "Germany", "Rua do Paço, 67", 69004, 37.28));
                order.Add(new Orders(orderId + 5, empId + 5, "DRACD", "Bern", "Germany", "Hauptstr. 31", 8010, 67.00));
                order.Add(new Orders(orderId + 6, empId + 6, "RATTC", "Genève", "USA", "Starenweg 5", 1204, 23.32));
                orderId += 6;
                empId += 6;
              }
              this.OrdersGrid.DataSource = order;
              this.OrdersGrid.DataBind();
          }
          [Serializable]
          public class Orders
          {
             public Orders()
             {

             }
             public Orders(int OrderId, int empId, string CustomerId, string shipCity, string shipCountry,string shipAddress,int shipPostalCode, double freight)
             {
                this.OrderID = OrderId;
                this.EmployeeID = empId;
                this.CustomerID = CustomerId;
                this.ShipCity = shipCity;                
                this.ShipCountry = shipCountry;
                this.ShipAddress=shipAddress;
                this.ShipPostalCode = shipPostalCode;
                this.Freight = freight;
             }
             public int OrderID { get; set; }
             public int EmployeeID { get; set; }
             public string CustomerID { get; set; }
             public string ShipCity { get; set; }
             public string ShipCountry { get; set; }
             public string ShipAddress { get; set; }
             public int ShipPostalCode { get; set; }
             public double Freight { get; set; }
          }
        }
      }
{% endhighlight  %}
{% endtabs %}

The following output is displayed as a result of the above code example.

 ![Infinite Mode](Scrolling_images/Scrolling_img9.png)


