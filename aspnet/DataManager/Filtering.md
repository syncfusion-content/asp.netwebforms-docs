---
layout: post
title: Filtering | DataManager | ASP.NET Webforms | Syncfusion
description: filtering
platform: aspnet
control: DataManager
documentation: ug
keywords: filter Operators, lessThan, lessThanOrEqual, less, contains
---

# Filtering

Filtering is a basic technique in DataManager query. The “where” query is used to filter some particular or related records from the data source to review details of records. 

## Filter Operators

Filter operators are used to specify the filter type. The various filter operators corresponding to the type of the column is listed in the following table.

<table>
<tr>
<th>
Column type</th><th>
Filter operators</th></tr>
<tr>
<td>
Number</td><td>
ej.FilterOperators.greaterThan<br/>ej.FilterOperators.greaterThanOrEqual<br/>ej.FilterOperators.lessThan<br/>ej.FilterOperators.lessThanOrEqual<br/>ej.FilterOperators.equal</td></tr>
<tr>
<td>
String</td><td>
ej.FilterOperators.startsWith<br/>ej.FilterOperators.endsWith<br/>ej.FilterOperators.contains<br/>ej.FilterOperators.equal<br/>ej.FilterOperators.notEqual</td></tr>
<tr>
<td>
Boolean</td><td>
ej.FilterOperators.equal<br/>ej.FilterOperators.notEqual</td></tr>
<tr>
<td>
Date</td><td>
ej.FilterOperators.greaterThan<br/>ej.FilterOperators.greaterThanOrEqual<br/>ej.FilterOperators.lessThan<br/>ej.FilterOperators.lessThanOrEqual<br/>ej.FilterOperators.equal</td></tr>
</table>

## lessThan

This operator is used to get the records with values less than that of the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">
        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('OrderID', 'lessThan', 10252, false)">
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

![](Filtering_images/Filtering_img1.png)

## greaterThan

This operator is used to get the records with values greater than that of the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">
        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('OrderID', 'greaterThan', 10252, false).take(5)">
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

![](Filtering_images/Filtering_img2.png)

## lessThanOrEqual

This operator is used to get the records with values less than or equal to the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('OrderID', 'lessThanOrEqual', 10252, false).take(5)">
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

![](Filtering_images/Filtering_img3.png)

## greaterThanOrEqual

This operator is used to get the records with values greater than or equal to the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">
        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('OrderID', 'greaterThanOrEqual', 10252, false).take(5)">
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

![](Filtering_images/Filtering_img4.png)

## equal

This operator is used to get the records with values equal to that of the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">
        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('EmployeeID', 'equal', 4, false).take(4)">
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

![](Filtering_images/Filtering_img5.png)

## notEqual

This operator is used to get the records with values not equal to that of the filter value specified.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('EmployeeID', 'notEqual', 4, false).take(5)">
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

![](Filtering_images/Filtering_img6.png)

## contains

This operator is used to get the records that contains the filter value.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('CustomerID', 'contains', 'A', false).take(5)">
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

![](Filtering_images/Filtering_img7.png)

## startswith

This operator is used to get the records that starts with the filter value specified.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('CustomerID', 'startswith', 'A', false).take(5)">
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

![](Filtering_images/Filtering_img8.png)

## endswith

This operator is used to get the records that ends with the filter value specified.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query().where('CustomerID', 'endswith', 'A', false).take(5)">
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

![](Filtering_images/Filtering_img9.png)

## Predicate

## and predicate

The “and” predicate is used to add n-number of predicates with “and” condition and filter the data.

{% highlight html %}

    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query()
            .where(ej.Predicate('OrderID', ej.FilterOperators.greaterThan, 10399, true).and('CustomerID', ej.FilterOperators.startsWith, 'V', true)).take(5)">
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

![](Filtering_images/Filtering_img10.png)

## or predicate

By using this method you can add n-number of predicates with “or” condition and filter the data.

{% highlight html %}
 
    <asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">

        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
             Query = "ej.Query()
            .where(ej.Predicate('OrderID', ej.FilterOperators.greaterThan, 10399, true).or('CustomerID', ej.FilterOperators.startsWith, 'V', true)).take(5)">
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

![](Filtering_images/Filtering_img11.png)

## Containment Operators

### notcontains

This operator is used to get the records that not contains the filter value.

{% highlight html %}

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/>
        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
                Query = "ej.Query()
                .from('Orders').select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCountry')
                .page(1,5).where('ShipCountry', 'notcontains', 'CAN', false)">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
                <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
                <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
            </Columns>
        </ej:Grid>
    {% endhighlight %}

![](Filtering_images/Filtering_image12.png) 

### contains

This operator is used to get the records that contains the filter value.

{% highlight html %}

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
        Query = "ej.Query()
        .from('Orders').select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCountry')
        .page(1,5).where('ShipCountry', 'contains', 'CAN', false)">
    <Columns>
        <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
        <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
        <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
        <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
        <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
    </Columns>
    </ej:Grid>

{% endhighlight %}

![](Filtering_images/Filtering_image111.png) 

### in

This operator used to fetch the records with value match with the given filter value. 

{% highlight html %}

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query()
            .from('Orders').select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCountry')
            .page(1,5).where('ShipCountry', 'IN', ['INDIA'], false)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

{% endhighlight %}

![](Filtering_images/Filtering_image13.png) 

### notin

This operator used to fetch the records with value not match with the given filter value. 

{% highlight html %}

    <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/>
    <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"
            Query = "ej.Query()
            .from('Orders').select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCountry')
            .page(1,5).where('ShipCountry', 'notin', ['INDIA'], false)">
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

{% endhighlight %}

![](Filtering_images/Filtering_image14.png) 

![](Filtering_images/Filtering_image15.png) 

## Lambda Operators

### all

The ALL operator returns true if all the sub query values meet the condition. This operator used to fetch the records of the fields match with the given value’s fields.

{% highlight html %}

    <ej:Grid ID="OrdersGrid" runat="server" >
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

{% endhighlight %}

{% highlight javascript %}

    setTimeout(function () {
        var gridData = [{ OrderID: 10248, CustomerID: "VINET", EmployeeID: 5, OrderDate: new Date(8364186e5), ShipName: "Vins et alcools Chevalier", ShipCity: "Reims", ShipAddress: "59 rue de l'Abbaye", ShipRegion: null, ShipPostalCode: "51100", ShipCountry: "France", Freight: 32.38, Verified: !0 }];
        var data = [{ OrderID: 10248, CustomerID: "VINET", EmployeeID: 5, OrderDate: new Date(8364186e5), ShipName: "Vins et alcools Chevalier", ShipCity: "Reims", ShipAddress: "59 rue de l'Abbaye", ShipRegion: null, ShipPostalCode: "51100", ShipCountry: "France", Freight: 32.38, Verified: !0 }];
        var dataManager = ej.DataManager(gridData);
        var source = ej.DataManager(data);
        var result = ej.Query().select("ShipCountry")
        var ShipCountry = source.executeLocal(result);
        var query = ej.Query()
            .where("ShipCountry", "equal all", ShipCountry, false).select("OrderID", "CustomerID", "EmployeeID", "Freight", "ShipCountry");

        var execute = dataManager.executeLocal(query); // executing query
        var obj = $("#MainContent_OrdersGrid").ejGrid("instance");
        obj.dataSource(execute);
    }, 1000);

{% endhighlight %}

![](Filtering_images/Filtering_image16.png) 

### any

The ANY operator returns true if any of the sub query values meet the condition. The returned data match with any one of the field in existing table.

{% highlight html %}

    <ej:Grid ID="OrdersGrid" runat="server" >
        <Columns>
            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
            <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />
            <ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" />
            <ej:Column Field="ShipCountry" HeaderText="Ship City" Width="75" />
            <ej:Column Field="Freight" HeaderText="Freight" Width="75" />
        </Columns>
    </ej:Grid>

{% endhighlight %}

{% highlight javascript %}

    setTimeout(function () {
        var gridData = window.gridData;
        var data = [{ OrderID: 10343, CustomerID: "LEHMS", EmployeeID: 4, OrderDate: new Date(8467002e5), ShipName: "Lehmanns Marktstand", ShipCity: "Frankfurt a.M.", ShipAddress: "Magazinweg 7", ShipRegion: null, ShipPostalCode: "60528", ShipCountry: "Germany", Freight: 110.37, Verified: !0 }, { OrderID: 10344, CustomerID: "WHITC", EmployeeID: 4, OrderDate: new Date(8467866e5), ShipName: "White Clover Markets", ShipCity: "Seattle", ShipAddress: "1029 - 12th Ave. S.", ShipRegion: "WA", ShipPostalCode: "98124", ShipCountry: "USA", Freight: 23.29, Verified: !1 }];
        var dataManager = ej.DataManager(gridData);
        var source = ej.DataManager(data);
        var result = ej.Query().select("ShipCountry")
        var ShipCountry = source.executeLocal(result);
        var query = ej.Query()
            .where("ShipCountry", "equal any", ShipCountry, false).select("OrderID", "CustomerID", "EmployeeID", "Freight", "ShipCountry");
        var execute = dataManager.executeLocal(query); // executing query
        $("#table1 tbody").html($("#tableTemplate").render(execute));
        var obj = $("#MainContent_OrdersGrid").ejGrid("instance");
        obj.dataSource(execute);
    }, 1000);

{% endhighlight %}

![](Filtering_images/Filtering_image17.png) 

