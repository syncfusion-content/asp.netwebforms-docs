---
layout: post
title: Advanced Functionalities  | DataManager | ASP.NET Webforms | Syncfusion
description: Advanced Functionalities
platform: aspnet
control: DataManager
documentation: ug
keywords: Offline Support, Load on Demand, Customer Request Headers, HTML Table, Cross domain & JSONP

---
# Advanced Functionalities

## Offline Support

Offline support allows data-bound Syncfusion UI widgets to function without active server connection. Users can continue working with the data.

With offline as true, the DataManager requests the server only once and further data manipulation operation can be done at client side itself.

In the following code example, the offline property of the DataManager is set as true.

{% highlight html %}

   <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"/>

         <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 
            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

    </asp:Content>

{% endhighlight %}

![](Data-Binding_images/Data-Binding_img8.png)

## Load on demand

Load on demand is powerful technique to reduce band width size of consuming data. It allow you to retrieve the required range of data alone from the server and this feature helps you when the server contains large amount of data.

You can use the following code example for implementing load on demand using DataManager.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 
            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).page(1,3)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

    pageIndex: <input id="pageIndex" type="text" placeholder="page index" />

    pageSize:  <input id="pageSize" type="text" placeholder="page size" />

    <ej:Button runat="server" Type="Button" Text="Loadondemand" ClientSideOnClick="onClick" ID="submit"></ej:Button>

    </asp:Content>

    <asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        function onClick(e)
        {
            var from = parseInt($("#pageIndex").val());
            var to = parseInt($("#pageSize").val());
            var obj = $("#MainContent_OrdersGrid").ejGrid("instance")
            tempQuery = new ej.Query();
            tempQuery.page(from, to);
            var dm = window.FlatData.executeQuery(tempQuery).done(function (e1) {
                obj.dataSource(e1.result);
            })
        }

    </script>

    </asp:Content>

{% endhighlight %}

The result of the above code example is illustrated as follows.

![](Data-Binding_images/Data-Binding_img9.png)

Load on demand {:.caption}

The request and the response for the above code is send as follows.


![](Data-Binding_images/Data-Binding_img10.png)


Demanded data {:.caption}

## Custom Request Headers

You can add custom request headers using **DataManager** and the headers can be added to the request headers in three ways that is illustrated in the following code example.

### Adding Custom Request Headers to every Request using headers

You can add custom request headers to every request made by the **DataManager** using the `headers` property. Refer to the following code example for setting the custom request headers using the `headers` property.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true" Offline="true" Headers="new List<Dictionary<string, object>> { new Dictionary<string, object>() { { "myData", 3232323 } } }"/>

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

    </asp:Content>

{% endhighlight %}

The above method generates the request header with custom header as follows.

![](Advanced_images/headers1.png) 

### Adding Custom Request Headers to every Request using pre-request callback **beforeSend**

You can set the custom headers using pre-request callback **beforeSend** as follows. The **setRequestHeader** method can be used to modify the **XMLHTTPRequest**.

{% highlight C# %}

    public partial class DataManager : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {

        }
        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object Data(int skip, int take)
        {

            var DataSource = OrderRepository.GetAllRecords();
            DataResult ds = new DataResult();
            ds.result = DataSource.Skip(skip).Take(take);
            ds.count = ds.count = DataSource.Count();
            return ds;
        }
    }

{% endhighlight %}

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager runat="server" ID="FlatData" URL="Default.aspx/Data" Adaptor="UrlAdaptor"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 
            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

    </asp:Content>

    <script type="text/javascript">
        $(function () {
             var customAdaptor = new ej.UrlAdaptor().extend({
                beforeSend: function (request, settings) {
                    settings.setRequestHeader("myData1", "Syncfusion");
                    settings.setRequestHeader("myData2", 23243);
                }
            });
            window.FlatData.adaptor = new customAdaptor();
            var gridObj = $("#MainContent_OrdersGrid").ejGrid("instance");
            gridObj.dataSource(window.FlatData.executeQuery(new ej.Query().take(7)));

        });
    </script>
  
{% endhighlight %}

The above method generates the request header with custom header as follows.

![](Advanced_images/headers3.png)

### Adding Custom Request Headers using **addParams** method

You can use the addParams method of ej.Query class, to add custom parameter to the data request.

{% highlight html %}

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true" />

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 
            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).where('CustomerID', 'equal', 'VINET').take(5).addParams('Syncfusion', true)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

{% endhighlight %}

The custom parameter will be passed along with the data request of the grid as follows.

![](Advanced_images/headers2.png) 

## Cross domain & JSONP

The **DataManager** contains support for creating cross domain request, you can achieve this by using `crossDomain` and `jsonp` property of the **DataManager**. The following code example illustrate on how to create cross domain request. 

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true"/>

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 
            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">
            <Columns>
                    <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                    <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                    <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
                    <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
                    <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>

    </asp:Content>

{% endhighlight %}

Result of above code example is illustrated as follows.

![](Data-Binding_images/Data-Binding_img12.png) 

## HTML Table

Other than **JSON** and **Remote** datasource, the **DataManager** can also fetch and use data from **HTML** element. You can achieve this by using the **table** property of the **DataManager**. The **DataManager** can fetch data from the **HTML** table element.

Refer to the following code example for the **HTML** element binding using **DataManager**.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <script id="_table1" type="text/template">

        <table id="datasource" style="display:none">
            <thead>
                <tr>
                    <th>OrderID</th>
                    <th>EmployeeID</th>
                    <th>CustomerID</th>
                </tr>
            </thead>
            <tbody>
                <tr><td>10248</td><td>VINET</td><td>5</td></tr>
                <tr><td>10249</td><td>TOMSP</td><td>6</td></tr>
                <tr><td>10250</td><td>HANAR</td><td>4</td></tr>
                <tr><td>10251</td><td>VICTE</td><td>3</td></tr>
                <tr><td>10252</td><td>SUPRD</td><td>4</td></tr>
            </tbody>
        </table>

    </script>

        <ej:DataManager ID="FlatData" runat="server" Table="#_table1" />

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />
            </Columns>
        </ej:Grid>

</asp:Content> 

{% endhighlight %}

The result of the above code example is illustrated as follows.

![](Data-Binding_images/Data-Binding_img13.png)


