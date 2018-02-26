---
layout: post
title: Virtual Scrolling | ListView | ASP.NET Webforms | Syncfusion
description: virtual scrolling
platform: aspnet
control: ListView
documentation: ug
---

# Virtual Scrolling

   We can load large data on demand using "AllowVirtualScrolling" property. By default, "AllowVirtualScrolling" set as boolean value of **"false"**. When it is set true, list items will be loaded on every scroll action. The number of items to be loaded per request can be specified using the “ItemRequestCount” property. We have provided two type of option for virtualScrolling,

## Normal Mode
    This mode allows you to load the list view data while scrolling i.e. each time the scroll bar is scrolled, it will send request to the server to load the data.

## Continuous Mode
    This mode allows you to load the list view data when the scrollbar reaches the end point. In this mode, we can specify the number of items to be loaded per request.

Please refer the following code examples.

{% highlight html %} 

     <ej:ListView ID="List" runat="server" ShowHeader="false" Width="200" Height="200" Query="ej.Query().from('Customers')" DataTextField="CustomerID" AllowVirtualScrolling="true" VirtualScrollMode="Continuous" >
                <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/" CrossDomain="true" />           
            </ej:ListView>

 {% endhighlight %}
