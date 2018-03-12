---
layout: post
title: Getting started with Pager 
description: getting started
platform: aspnet
control: Pager
documentation: ug
---

# Getting Started

This section briefly explains about how to create a **Pager** control in your application with ASP.NET.

# Adding scroller control in your ASP.NET application

1.	Create an ASP.NET Project and add required assemblies, scripts and styles to it referring [ASP-Getting Started](https://help.syncfusion.com/aspnet/getting-started) documentation.

2.	The Essential ASP.NET Pager control is based on total records count, page size and page count values. Add the following code example to the corresponding view pages to render the Pager control in your ASP.NET application. 

**TotalRecordsCount:** totalRecordsCount defines the total number of records which is bounded as a single data.

{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="20" runat="server"></ej:Pager>
        
{% endhighlight %}

Run the above sample to get the below output.

![pager](Getting-Started_images/Getting-Started_img1.png)


 **PageSize:**  pageSize value defines the number of records to be displayed per page. The default value for the pageSize API is 12. 
 
 N> The page count value changes with change in the pageSize value.

  {% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="20" PageSize="1" runat="server"></ej:Pager>

{% endhighlight %}

Run the above sample to get the below output.

![pager](Getting-Started_images/Getting-Started_img2.png)

**PageCount:**  pageCount value defines the number of pages to be displayed in the pager control for navigation. The default value for pageCount is 10 and value will be updated based on totalRecordsCount and pageSize values.

{% highlight javascript %}

    <ej:Pager ID="Pager" TotalRecordsCount="20" PageSize="1" PageCount="3" runat="server"></ej:Pager>
{% endhighlight %}

Run the above sample to get the below output.

![pager](Getting-Started_images/Getting-Started_img3.png)

