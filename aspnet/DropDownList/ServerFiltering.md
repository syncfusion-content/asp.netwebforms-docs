---
layout: post
title: Server Filtering in the DropDownList control for Syncfusion ASP.NET WebForm
description: Descripes about the server filtering in the DropDownList control for Syncfusion ASP.NET WebForm
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Filtering, Server Filtering
---

# Server Filtering

Server filtering for displaying only a fixed amount of dataset from the whole dataset. In general, DropDownList displays just the data returned from the server. This feature is convenient for you to apply when the user does not want to see the whole dataset in the popup wrapper.
EnableServerFiltering If set to true, the filtering operations performed in the remote service and returns the result.

{% highlight html %}

    <ej:DropDownList ID="selectCompany" DataTextField="CompanyName"  DataValueField="ContactName" runat="server" Width="230" ShowCheckbox="true" EnableFilterSearch="true" EnableServerFiltering="true" EnablePopupResize="true" WatermarkText="Select a company">
        <DataManager URL="//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Customers" CrossDomain="true"  />
    </ej:DropDownList>

{% endhighlight %}

![](ServerFiltering_images/ServerFiltering_image3.png)

This sample raises the query on Customer service. Returns ContactName records for customers with ContactName containing the string “c”.

![](ServerFiltering_images/ServerFiltering_image1.png)

