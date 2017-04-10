---
layout: post
title: Sorting | DataManager | ASP.NET Webforms | Syncfusion
description: sorting
platform: aspnet
control: DataManager
documentation: ug
keywords: sorting, multi sorting, dynamic sorting, SortBy
---

# Sorting

## Default 

Sorting is basic query in DataManager. It enables you to view the items or records in ascending or descending order based on particular field and sorting direction specified. The query parameter of DataManager enables you to retrieve the data in the sorted fashion and thus utilizing the resultant data obtained.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query().sortBy('CustomerID', ej.sortOrder.Ascending, false).take(5)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Sorting_images/Sorting_img1.png)

## SortByDesc

The sortByDesc query of the data manager is used to sort the specified field in descending order by default. You can use the following code example for sortByDesc query.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query().sortByDesc('EmployeeID').take(5)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Sorting_images/Sorting_img2.png)

## Dynamic sorting

The table can be dynamically sorted by using an external button click event. You can sort the value of the column by using the sortBy query and thus the sorted data is retrieved and bounded to the table. The following code example illustrates you to dynamically sort the data source.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query().sortByDesc('EmployeeID').take(10)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

    <input id="field" type="text" placeholder="fieldName" />

    <ej:Button runat="server" Type="Button" Text="Sort" ClientSideOnClick="onClick" ID="submit"></ej:Button>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        function onClick(e) {
            var field = $("#field").val();
            var obj = $("#MainContent_OrdersGrid").ejGrid("instance")
            var query = ej.Query().sortByDesc(field).take(5)
            var dm = window.FlatData.executeQuery(query).done(function (e1) {
                obj.dataSource(e1.result);
            })
        }

    </script>

</asp:Content>

{% endhighlight %}

Result of above code example is illustrated as follows.

![](Sorting_images/Sorting_img3.png)

## Multi sorting

Multi sorting is a special technique, where you can sort multiple fields by adding multiple sorting queries to DataManager.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query().sortByDesc('EmployeeID').sortBy('EmployeeID', 'ascending').take(5)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid> 

</asp:Content>

{% endhighlight %}

Result of above code example is illustrated as follows.

![](Sorting_images/Sorting_img4.png)



