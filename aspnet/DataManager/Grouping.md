---
layout: post
title: Grouping | DataManager | ASP.NET Webforms | Syncfusion
description: grouping
platform: aspnet
control: DataManager
documentation: ug
---

# Grouping

Grouping technique is also supported in DataManager. When you want to analyze any particular record based on its category, you can simply group that column and analyze the records based on category. The following code example illustrates the grouping behavior in table.

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">



        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders"/>

        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

             Query = "ej.Query()

            .page(1,5)

            .group('CustomerID')">



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

![](Grouping_images/Grouping_img1.png)



