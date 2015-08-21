---
layout: post
title: Load-on-Demand-support
description: load-on-demand support 
platform: aspnet
control: Control Name undefined
documentation: ug
---

# Load-on-Demand support 

ListBox widget provides the Load-onDemand support, when binding the remote data for the ListBox. It loads partially, only a set of data from remote server loaded initially, and imports data further upon loading. To enable Load-onDemand support, set the EnableLoadOnDemand property as true. You can set ItemsCount that specifies number of items in the ListBox. You can load any number of items upon request with ItemRequest ClientSide Event.

The following steps explain you the behaviour of Load-onDemand support in ListBox.

In an ASPX page, add an element to configure ListBox.


{% highlight html %}

<div class="control">

    <div class="ctrllabel">

        Select Customer ID</div>

    <div class="control1" style="float: left;">

        <ej:listbox id="listboxsample" DataTextField="CustomerID"  ClientSideOnItemRequest="itemRequested" EnableLoadOnDemand="true"

ItemsCount="91" runat="server">

 </ej:listbox>

    </div>

</div>



{% endhighlight %}



{% highlight c# %}

        protected void Page_Load(object sender, EventArgs e)

        {

            this.listboxsample.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";

            this.listboxsample.Query = "ej.Query().from('Customers')";    

        }



{% endhighlight %}



{% highlight js %}

function itemRequested(args) {

        var target = $("#<%=listboxsample.ClientID%>").data("ejListBox");

        target.model.query = ej.Query().from("Customers").range(args.start, args.start + 20);

        this.model.itemsCount = 20; //to load 20 items

    }





{% endhighlight %}



Output of the above steps.


 ![C:/Users/Rajaveni/Desktop/docs/LD/LD.png](Load-on-Demand-support_images/Load-on-Demand-support_img1.png)



