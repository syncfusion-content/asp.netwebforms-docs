---
layout: post
title: Summary | DataManager | ASP.NET Webforms | Syncfusion
description: summary 
platform: aspnet
control: DataManager
documentation: ug
keywords: Sum, Average, Minimum, Maximum, Distinct
---

# Summary 

Summary is a key feature in DataManager that helps to aggregate any data. DataManager provides several summary type by default, they are as follows.

* Sum
* Average 
* Minimum
* Maximum
* Distinct

The ej provided several data utilization methods to achieve summary. 

## Sum

The Sum summary type provides the sum of the data. The Sum data utilization method accepts two parameters, they are JSON data and the field name where the sum is calculated. The following code example illustrates the Default Summary Types.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
                .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')
                .range(25,30)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>

    </ej:Grid>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        setTimeout(function () {
            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");
            var data = proxy._currentJsonData;
            var sum = ej.sum(data, "EmployeeID");//Calculates the sum EmployeeID
            $("body").append("<span>Sum:" + sum + "</spn>");
        }, 3000);

    </script>

</asp:Content>

{% endhighlight %}

The result of the above code example is illustrated as follows.

![](Summary_images/Summary_img1.png)

## Min

The Minimum of a particular field can be calculated by using the ej.min data utilization method and this method accepts the arguments such as JSON data/array, field name and the comparer used for the comparison. When the data to the min method is a JSON array then the whole record is returned.

The minimum of particular field can be calculated as follows.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
                .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')
                .range(25,30)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        setTimeout(function () {
            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");
            var data = proxy._currentJsonData;
            var min = ej.min(data, "EmployeeID");//Calculates the min EmployeeID
            $("body").append("<span>Min:" + min.EmployeeID + "</spn>");
        }, 3000);

    </script>

</asp:Content>

{% endhighlight %}

The result of the above code example is illustrated as follows.

![](Summary_images/Summary_img2.png)

## Max

The Maximum of a particular field can be calculated by using the ej.max data utilization method and this method accepts the arguments such as JSON data/array, field name and the comparer used for the comparison. When the data to the max method is a JSON array then the whole record is returned.

The maximum of particular field can be calculated as follows.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
                .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')
                .range(25,30)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        setTimeout(function () {
            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");
            var data = proxy._currentJsonData;
            var max = ej.max(data, "EmployeeID"); //Calculates the max Freight
            $("body").append("<span>Max:" + max.EmployeeID + "</spn>");
        }, 3000);

    </script>

</asp:Content>

{% endhighlight %}

The result for the above code example is illustrated as follows.

![](Summary_images/Summary_img3.png)

## Avg

The Average summary type provides the average of the given data. The Average data utilization method accepts two parameters, JSON/Array data and the field name where the sum is calculated. Use the following code example for calculating the average of given JSON data.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
                .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')
                .range(25,30)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">
        setTimeout(function () {
            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");
            var data = proxy._currentJsonData;
            var avg = ej.avg(data, "EmployeeID");//Calculates the avg EmployeeID
            $("body").append("<span>Avg:" + avg + "</spn>");
        }, 3000);
    </script>

</asp:Content>

{% endhighlight %}

The result of the above code example is illustrated as follows.

![](Summary_images/Summary_img4.png)

## Distinct

In a data, a field may contain many duplicate values; and sometimes to list the different (distinct) values you can use the ej.distinct method. This method accepts three parameters such as JSON/Array data, fieldname that you want to fetch as distinct and the third boolean parameter when set as true, returns the whole record when the data is a JSON array. 

The following code example illustrates how to use the ej.distinct method. 

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
                .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')
                .range(25,35)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server">

    <script type="text/javascript" class="jsScript">

        setTimeout(function () {
            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");
            var data = proxy._currentJsonData;
            var distinct = ej.distinct(data, "EmployeeID", true);//Calculates the distinct for EmployeeID
            proxy.dataSource(distinct);
        }, 3000);

    </script>

</asp:Content>

{% endhighlight %}

The result for the above code example is illustrated as follows.

![](Summary_images/Summary_img5.png)



