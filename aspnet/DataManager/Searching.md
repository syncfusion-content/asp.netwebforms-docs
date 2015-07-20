---
layout: post
title: Searching
description: searching
platform: aspnet
control: DataManager
documentation: ug
---

# Searching

Searching is a basic query technique in data manager. It is used to filter the records from the entire data source based on the search key parameter.

{% highlight html %}

&lt;asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent"&gt;



        &lt;ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/&gt;

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query().search(4, 'EmployeeID').take(5)">



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

![](Searching_images/Searching_img1.png)
{:.image }


