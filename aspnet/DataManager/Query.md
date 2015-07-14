---
layout: post
title: Query
description: query
platform: aspnet
control: DataManager
documentation: ug
---

## Query

DataManager provides support for multiple queries to perform various operations like filtering, sorting, cloning, expanding, searching, grouping etc., in the data source. Here, you can learn the query options in detail.

Select

The “select” query of the data manager is used to select only some particular fields or columns from the data source. The following code example illustrates on how to select only particular fields using the select query.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        &lt;ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" Query ="new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)"&gt;

            &lt;%--&lt;ClientSideEvents Load="OnLoad" /&gt;--%>

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



{ ![](Query_images/Query_img1.png) | markdownify }
{:.image }


From

The “from” query of the data manager is used to select the table from where the data is retrieved and bound to the table. The following code example illustrates on how to use the “from” query.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/&gt;



        &lt;ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" Query ="new ej.Query().from('Orders').select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)"&gt;

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

{ ![](Query_images/Query_img2.png) | markdownify }
{:.image }


Clone

The “clone” query of the data manager is used to duplicate the query. The following code example illustrates on how to clone a query.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        &lt;ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData" Query = "new ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(10)"&gt;

            &lt;ClientSideEvents ActionComplete="OnComplete" /&gt;

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

    &lt;script type="text/javascript" class="jsScript"&gt;

        var flag = true;

        function OnComplete() {

            if (flag) {

                flag = flase;

                var query = ej.Query().select(['OrderID', 'CustomerID', 'EmployeeID', 'ShipCity', 'Freight']).take(5)

                var query1 = query.clone();

                var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");

                var dm = window.FlatData.executeQuery(query1).done(function (e1) {

                    proxy.dataSource(e1.result);

                })

            }

        }

&lt;/script&gt;

&lt;/asp:Content&gt;



Result of the above code example is illustrated as follows.

{ ![](Query_images/Query_img3.png) | markdownify }
{:.image }


Expand

The “expand” query of the data manager is used to perform complex data binding.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().from('Orders').

             select(['OrderID', 'CustomerID', 'Employee.FirstName', 'ShipCity', 'Freight']).take(5).expand('Employee')">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="Employee.FirstName" HeaderText="Emp Name" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



Result of the above code example is illustrated as follows.



{ ![](Query_images/Query_img4.png) | markdownify }
{:.image }


