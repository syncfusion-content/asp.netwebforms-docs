---
layout: post
title: Data-Adaptors
description: data adaptors
platform: aspnet
control: DataManager
documentation: ug
---

## Data Adaptors

DataManger uses adaptors to process data. There are three types of adaptors in DataManger. They are

* JSON Adaptor
* Url Adaptor
* OData Adaptor

JSON Adaptor

JSONAdaptor is used to process JSON data. It contains methods to process the given JSON data based on the queries. The following code example illustrates on how to use JSONAdaptor.

[ASPX]

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" Adaptor="JsonAdaptor"/&gt;



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

[CS]

public partial class DataManager : System.Web.UI.Page

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

                order.Add(new Orders(code + 1, "TOMSP", i + 0, 2.3 * i, "Münster"));

                order.Add(new Orders(code + 2, "HANAR", i + 2, 3.3 * i, "Rio de Janeiro"));

                order.Add(new Orders(code + 3, "VICTE", i + 1, 4.3 * i, "Lyon"));

                order.Add(new Orders(code + 4, "VINET", i + 3, 5.3 * i, "Reims"));

                order.Add(new Orders(code + 5, "SUPRD", i + 4, 6.3 * i, "Charleroi"));

                code += 5;

            }

            this.FlatData.Json = order;

            this.OrdersGrid.DataBind();



        }

        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.ShipCity = ShipCity;



            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public string ShipCity { get; set; }



        }

    }



The result of above code example is illustrated as follows.

{ ![](Data-Adaptors_images/Data-Adaptors_img1.png) | markdownify }
{:.image }


URL Adaptor

Url Adaptor of DataManager can be used when you want to use remote service to retrieve data. It interacts with server-side for all DataManager Queries and CRUD operations. Now, in the following code example the data is retrived from MVC Controller. 

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager runat="server" ID="FlatData" URL="Default.aspx/Data" Adaptor="UrlAdaptor"/&gt;

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

{ ![](Data-Adaptors_images/Data-Adaptors_img2.png) | markdownify }
{:.image }


OData Adaptor

Odata Adaptor that is extended from Url Adaptor, is used for consuming data through oData Service. You can use the following code example to use oData adaptor.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" CrossDomain="true" Offline="true"/&gt;

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

{ ![](Data-Adaptors_images/Data-Adaptors_img3.png) | markdownify }
{:.image }


WebAPI Adaptor

WebApi Adaptor, extended from UrlAdaptor, of DataManager is used for retrieving data from WebApi service. Refer to the following code example.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;

        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/UGService/api/Orders" CrossDomain="true" Adaptor="WebApiAdaptor"/&gt;

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



Result of the above code example is illustrated as follows.



{ ![](Data-Adaptors_images/Data-Adaptors_img4.png) | markdownify }
{:.image }


RemoteSave Adaptor

RemoteSaveAdaptor, extended from JsonAdaptor of DataManager, is used for binding local data and performs all DataManager queries in client-side. It interacts with server-side only for CRUD operations to pass the modified records. Refer to the following code example.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" Adaptor="remoteSaveAdaptor"/&gt;



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



public partial class DataManager : System.Web.UI.Page

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

                order.Add(new Orders(code + 1, "TOMSP", i + 0, 2.3 * i, "Münster"));

                order.Add(new Orders(code + 2, "HANAR", i + 2, 3.3 * i, "Rio de Janeiro"));

                order.Add(new Orders(code + 3, "VICTE", i + 1, 4.3 * i, "Lyon"));

                order.Add(new Orders(code + 4, "VINET", i + 3, 5.3 * i, "Reims"));

                order.Add(new Orders(code + 5, "SUPRD", i + 4, 6.3 * i, "Charleroi"));

                code += 5;

            }

            this.FlatData.Json = order;

            this.OrdersGrid.DataBind();



        }

        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.ShipCity = ShipCity;



            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public string ShipCity { get; set; }



        }

    }



Result of the above code example is illustrated as follows.



{ ![](Data-Adaptors_images/Data-Adaptors_img5.png) | markdownify }
{:.image }


Custom Adaptor

Custom adaptor is a key technique to customize adaptors in DataManager. Normally ej.Adaptor is base class for all the adaptors. Therefore, first inherit ej.Adaptor to develop customized one and then you can override the functionality in custom adaptor with base class. Refer to the following code example.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server"/&gt;



        &lt;ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" &gt;

            &lt;ClientSideEvents Load="OnLoad" /&gt;

            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



&lt;asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server"&gt;

    &lt;script type="text/javascript"&gt;

        $(function () {// Document is ready.

            //new custom adaptor implementation

            //able to implement more option in custom adaptor other than insert

            var customAdaptor = new ej.Adaptor().extend({

                insert: function (dm, data) {

                    return dm.dataSource.json.push(data);

                },

                processQuery: ej.JsonAdaptor.prototype.processQuery // reused process query from json adaptor

            });

            window.FlatData.Adaptor = new customAdaptor()

            window.FlatData.insert({ OrderID: 10240, CustomerID: "HANAR", EmployeeID: 3, ShipCity: "Reims", Freight: "23.4" });

            window.FlatData.insert({ OrderID: 10241, CustomerID: "HANAR", EmployeeID: 2, ShipCity: "Reimse", Freight: "21.4" });

            window.FlatData.insert({ OrderID: 10242, CustomerID: "VINET", EmployeeID: 5, ShipCity: "Lyon", Freight: "13.4" });

            var obj = $("#MainContent_OrdersGrid").ejGrid("instance");

            obj.dataSource(window.FlatData.executeLocal(new ej.Query().take(7)));

        })



    &lt;/script&gt;



&lt;/asp:Content&gt;



Result of above code example is as follows.

{ ![](Data-Adaptors_images/Data-Adaptors_img6.png) | markdownify }
{:.image }


