---
layout: post
title: Data-Binding
description: data binding
platform: aspnet
control: DataManager
documentation: ug
---

## Data Binding

LOCAL

A data source can be bound to a Grid through DataManager control. The DataManager supports JSON array binding. It is useful to bind records in client side by using JSON data that is very helpful in Single Page Application (SPA) and in feature rich web application. To achieve this, you can refer to the following code example.

&lt;%--connection local reference--%&gt;

&lt;ej:DataManager runat="server" ID="FlatData" URL="Default.aspx/Data"/&gt;



<ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;



[ASPX.CS]

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



The result of the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img1.png) | markdownify }
{:.image }


REST Services

OData binding

OData is standardized protocol for creating and consuming data. You can retrieve data from oData service by using DataManager. You can refer to the following code example of remote Data binding by using oData service.

&lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" /&gt;



<ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

&lt;/ej:Grid&gt;

The result of the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img2.png) | markdownify }
{:.image }


OData V4

The OData v4 is an improved version of OData protocols and the DataManager can also retrieve and consume OData v4 services.  For more details on OData v4 Services, refer to the [odata documentation](http://www.odata.org/documentation/odata-version-4-0/).

You can refer to the following code example for consuming OData v4 services and bind the result to the Grid. In the the following code, crossDomain is enabled to make cross domain request.

&lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true" /&gt;



<ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

&lt;/ej:Grid&gt;



The request and response to the service from the DataManager is illustrated as follows.

{ ![C:/Users/apoorvah.ramanathan/Desktop/1.png](Data-Binding_images/Data-Binding_img3.png) | markdownify }
{:.image }




The result of the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img4.png) | markdownify }
{:.image }


WebAPI binding

The Web API is a programmatic interface to define the request and response messages system that is mostly exposed in JSON or XML. The DataManager contains default adaptor to handle the Web API request and responses. The WebApiAdaptor is discussed briefly in the Adaptor section.

Refer to the following code example for consuming Web API data using DataManager.

&lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Adaptor="WebApiAdaptor"/&gt;



<ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;



The request to the Web API and response is illustrated as follows.

{ ![C:/Users/apoorvah.ramanathan/Desktop/1.png](Data-Binding_images/Data-Binding_img5.png) | markdownify }
{:.image }


The result for the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img6.png) | markdownify }
{:.image }


Other Web Services binding

The DataManager can also retrieve data from ASP.Net Web methods and ASP.Net MVC Controller`s action. You can achieve this by using the UrlAdaptor of DataManager. The UrlAdaptor is discussed briefly in the adaptor section.  By default, the Url Adaptor is used when accessing remote data. 

Refer to the following code example to know how the DataManager can be used to consume data from the web method.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="WebService1.asmx/getData"/&gt;

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;



&lt;/asp:Content&gt;



{ ![](Data-Binding_images/Data-Binding_img7.png) | markdownify }
{:.image }


Offline Mode

The offline mode is one of the useful feature of DataManager that can be enabled by setting offline property of the datamanager as true. With offline as true, the DataManager requests the server only once and further data manipulation operation can be done at client side itself.

In the following code example, the offline property of the DataManager is set as true.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"/&gt;



         <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;



&lt;/asp:Content&gt;



The result of the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img8.png) | markdownify }
{:.image }


Load on demand

Load on demand is powerful technique to reduce band width size of consuming data. It allows you to retrieve the required range of data alone from the server and this feature helps you when the server contains large amount of data.

You can use the following code example for implementing load on demand using DataManager.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true"/&gt;

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).page(1,3)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

    pageIndex: &lt;input id="pageindx" type="text" placeholder="pageindex" /&gt;

    pageSize:  &lt;input id="pagesize" type="text" placeholder="pagesize" /&gt;

    &lt;ej:Button runat="server" Type="Button" Text="Loadondemand" ClientSideOnClick="onClick" ID="submit"&gt;&lt;/ej:Button&gt;



&lt;/asp:Content&gt;

&lt;asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server"&gt;

&lt;script type="text/javascript" class="jsScript"&gt;

    function onClick(e)

    {

        var from = parseInt($("#pageindx").val());

        var to = parseInt($("#pagesize").val());

        var obj = $("#MainContent_OrdersGrid").ejGrid("instance")

        tempQuery = new ej.Query();

        tempQuery.page(from, to);

        var dm = window.FlatData.executeQuery(tempQuery).done(function (e1) {

            obj.dataSource(e1.result);

        })

    }

&lt;/script&gt;

 &lt;/asp:Content&gt;



The result of the above code example is illustrated as follows.

{ ![](Data-Binding_images/Data-Binding_img9.png) | markdownify }
{:.image }


The request and the response for the above code is as follows.

{ ![](Data-Binding_images/Data-Binding_img10.png) | markdownify }
{:.image }


Custom Request Headers

You can add custom request headers by using DataManager and the headers can be added to the request headers in two ways that is illustrated in the following code example.

You can add custom request headers to every request made by the DataManager by using the headers property. Refer to the following code example for setting the custom request headers by using the headersproperty.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Headers="[{'DataServiceVersion':'1.0','MaxDataServiceVersion':'1.0'}]"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



The above method generates the request header with custom header as follows.

{ ![](Data-Binding_images/Data-Binding_img11.png) | markdownify }
{:.image }


Cross domain & JSONP

The DataManager contains support for creating cross domain request, you can achieve this by using crossDomain and jsonp property of the DataManager. The following code example illustrate on how to create cross domain request. 

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" 

            Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



Result of above code example is illustrated as follows.



{ ![](Data-Binding_images/Data-Binding_img12.png) | markdownify }
{:.image }


Html Table

The DataManager can also fetch and use data from HTML element. You can achieve this by using the table property of the DataManager. The DataManager can fetch data from the HTML table element.

Refer to the following code example.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

    &lt;script id="_table1" type="text/template"&gt;

        &lt;table id="datasource" style="display:none"&gt;

            &lt;thead&gt;

                &lt;tr&gt;

                    <th>OrderID</th>

                    <th>EmployeeID</th>

                    <th>CustomerID</th>

                &lt;/tr&gt;

            &lt;/thead&gt;

            &lt;tbody&gt;

                &lt;tr&gt;<td>10248</td><td>VINET</td><td>5</td>&lt;/tr&gt;

                &lt;tr&gt;<td>10249</td><td>TOMSP</td><td>6</td>&lt;/tr&gt;

                &lt;tr&gt;<td>10250</td><td>HANAR</td><td>4</td>&lt;/tr&gt;

                &lt;tr&gt;<td>10251</td><td>VICTE</td><td>3</td>&lt;/tr&gt;

                &lt;tr&gt;<td>10252</td><td>SUPRD</td><td>4</td>&lt;/tr&gt;

            &lt;/tbody&gt;

        &lt;/table&gt;

    &lt;/script&gt;

&lt;ej:DataManager ID="FlatData" runat="server" Table="#_table1" /&gt;

        &lt;ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"&gt;



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;



            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt; 



The result of the above code example is illustrated as follows.



{ ![](Data-Binding_images/Data-Binding_img13.png) | markdownify }
{:.image }


