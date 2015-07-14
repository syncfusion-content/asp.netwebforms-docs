---
layout: post
title: Sorting
description: sorting
platform: aspnet
control: DataManager
documentation: ug
---

## Sorting

Default 

Sorting is basic query in DataManager. It enables you to view the items or records in ascending or descending order based on particular field and sorting direction specified. The query parameter of DataManager enables you to retrieve the data in the sorted fashion and thus utilizing the resultant data obtained.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().sortBy('CustomerID', ej.sortOrder.Ascending, false).take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



Result of the above code example is illustrated as follows.

{ ![](Sorting_images/Sorting_img1.png) | markdownify }
{:.image }


SortByDesc

The sortByDesc query of the data manager is used to sort the specified field in descending order by default. You can use the following code example for sortByDesc query.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().sortByDesc('EmployeeID').take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;



Result of the above code example is illustrated as follows.

{ ![](Sorting_images/Sorting_img2.png) | markdownify }
{:.image }


Dynamic sorting

The table can be dynamically sorted by using an external button click event. You can sort the value of the column by using the sortBy query and thus the sorted data is retrieved and bounded to the table. The following code example illustrates you to dynamically sort the data source.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().sortByDesc('EmployeeID').take(10)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

    &lt;input id="field" type="text" placeholder="fieldName" /&gt;

    &lt;ej:Button runat="server" Type="Button" Text="Sort" ClientSideOnClick="onClick" ID="submit"&gt;&lt;/ej:Button&gt;



&lt;/asp:Content&gt;

&lt;asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server"&gt;

    &lt;script type="text/javascript" class="jsScript"&gt;

        function onClick(e) {



            var field = $("#field").val();

            var obj = $("#MainContent_OrdersGrid").ejGrid("instance")

            var query = ej.Query().sortByDesc(field).take(5)



            var dm = window.FlatData.executeQuery(query).done(function (e1) {

                obj.dataSource(e1.result);

            })

        }

    &lt;/script&gt;

&lt;/asp:Content&gt;



Result of above code example is illustrated as follows.

{ ![](Sorting_images/Sorting_img3.png) | markdownify }
{:.image }


Multi sorting

Multi sorting is a special technique, where you can sort multiple fields by adding multiple sorting queries to DataManager.

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().sortByDesc('EmployeeID').sortBy('EmployeeID', 'ascending').take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt; 

&lt;/asp:Content&gt;



Result of above code example is illustrated as follows.

{ ![](Sorting_images/Sorting_img4.png) | markdownify }
{:.image }


