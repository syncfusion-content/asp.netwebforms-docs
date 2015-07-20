---
layout: post
title: Paging
description: paging
platform: aspnet
control: DataManager
documentation: ug
---

# Paging

Paging is a very important query in DataManager that is used to display only some records from the large data source. 

## Default

The paging index and the paging size parameters of the paging query determines the number of records to be retrieved from the data source of the DataManager.

Refer to the following code example for the paging options.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .page(5,5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result for the above code example is illustrated as follows.

![](Paging_images/Paging_img1.png)
{:.image }


## Dynamic Paging

The paging operation can be dynamically performed by using the DataManager. With the help of an external button click event, the required page records can be obtained and processed accordingly. The following code example illustrates the dynamic paging.

{% highlight html %}

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

    &lt;ej:Button runat="server" Type="Button" Text="Execute" ClientSideOnClick="onClick" ID="submit"&gt;&lt;/ej:Button&gt;



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

{% endhighlight %}

Result of above code example is illustrated as follows.

![](Paging_images/Paging_img2.png)
{:.image }


## Custom paging

In this section, you can learn how to use customized paging. The following code example illustrates the custom paging.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .addParams('PageNumber',5)

                    .addParams('PageSize',3)

                    .where('CustomerID', 'contains', 'A', false)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result of above code example is illustrated as follows.

![](Paging_images/Paging_img3.png)
{:.image }


## Skip

The skip query is used to skip some number of records.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .skip(100)

                    .take(5)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Paging_images/Paging_img4.png)
{:.image }


## Take

The take query is used to get some certain number of records from the data source of the DataManager.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .take(3)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Paging_images/Paging_img5.png)
{:.image }


## RequiresCount

The requiresCount query is used to get the count of the total number of records in the data source of the DataManager.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .page(1,3)

                    .requiresCount()">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Paging_images/Paging_img6.png)
{:.image }


## Range

The range query is used to get some particular range of records from the data source of the DataManager.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                    .select('OrderID', 'CustomerID', 'EmployeeID', 'Freight', 'ShipCity')

                    .range(25,30)">



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="EmployeeID" Width="75" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" Width="75" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

&lt;/asp:Content&gt;

{% endhighlight %}

Result of the above code example is illustrated as follows.

![](Paging_images/Paging_img7.png)
{:.image }


