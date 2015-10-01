---
layout: post
title: Hierarchical Query | DataManager | ASP.NET Webforms | Syncfusion
description: hierarchical query
platform: aspnet
control: DataManager
documentation: ug
---

# Hierarchical Query

The DataManager contains support to manage the hierarchical query. The hierarchical queries are commonly required when you use foreign key binding. The hierarchical query can be provided by using the hierarchical function. This method accepts two parameters such as the query and the selector function. 

## foreignKey

The foreignkey method of ej.Query can be used to refer to another table fields. The foreignkey method accepts one parameter that is the foreign key value. 

The following code example illustrates the hierarchical query and foreignkey method. 

{% highlight html %}

<asp:Content runat="server" ID="Content1" ContentPlaceHolderID="MainContent">



        <ej:DataManager ID="FlatData" runat="server" URL="http://mvc.syncfusion.com/Services/Northwnd.svc"/>



        <ej:Grid ID="OrdersGrid" runat="server"  DataManagerID="FlatData"

            Query = "ej.Query()

                   .from('Orders')

                   .search('TM', ['CustomerID', 'Employee.FirstName'])

                   .page(1, 4)

                   .hierarchy(

                       ej.Query()

                           .foreignKey('OrderID')

                           .from('Order_Details')

                           .sortBy('Quantity'),

                       function () {

                           // Selective loading of child elements

                           return [10410, 10492, 10949, 10742, 10975]

                       })

                   ">



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

The result for the above code example is illustrated as follows.

![](Hierarchical-Query_images/Hierarchical-Query_img1.png) 



