---
layout: post
title: Toolbar
description: toolbar 
platform: aspnet
control: Grid
documentation: ug
---

## Toolbar 

### Default buttons

Toolbar is one of the user interaction controls related with Grid. It is handy to use the Toolbar to trigger more actions. The default toolbar items created for Grid are:

* Add
* Edit
* Delete
* Update
* Cancel
* Search

If you want Toolbar items other than the above items, you can make it using customToolBarItems.

### Custom Toolbar action

Custom Toolbar is a key functionality, used to customize Toolbar elements. Here you can learn in detail about the Toolbar template and its actions in the Custom Toolbar category. In the following code example, ejDropDownList is used to filter records by category.



[ASP]



[aspx]



  &lt;script id="Refresh" type="text/x-jsrender"&gt;

        &lt;select id="products"&gt;

            <option value="">All</option>

            <option value="2">Drinks</option>

            <option value="4">Dairy Products</option>

            <option value="3">Packages</option>

        &lt;/select&gt;

    &lt;/script&gt;



&lt;ej:Grid ID="Grid1" runat="server" AllowScrolling="true"&gt;

        &lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Products"&gt;&lt;/DataManager&gt;

        &lt;Columns&gt;

            &lt;ej:Column Field="ProductID" HeaderText="Product ID" IsPrimaryKey="True" TextAlign="Right" Width="100" /&gt;

            &lt;ej:Column Field="ProductName" HeaderText="Product Name" Width="200" /&gt;

            &lt;ej:Column Field="QuantityPerUnit" HeaderText="Quantity" TextAlign="Right" Width="100" /&gt;

            &lt;ej:Column Field="UnitsOnOrder" HeaderText="UnitsOnOrder" Width="100" /&gt;

        &lt;/Columns&gt;

        &lt;ScrollSettings Height="300" Width="auto"&gt;&lt;/ScrollSettings&gt;

        &lt;ToolbarSettings ShowToolbar="true"&gt;

            &lt;CustomToolbarItem&gt;

                &lt;ej:CustomToolbarItem TemplateID="#Refresh" /&gt;

            &lt;/CustomToolbarItem&gt;

        &lt;/ToolbarSettings&gt;

    &lt;/ej:Grid&gt;

 [javascript]



&lt;script&gt;



        $(document).ready(function () {

            $("#products").ejDropDownList({

                selectedItemIndex: 0,

                change: "Change"

            });

        });



        function Change(args) {

            var gridObj = $("#Grid1").data("ejGrid");

            if (this.getSelectedValue() != "")

                $("#Grid1").ejGrid("model.query", new ej.Query().where("CategoryID", ej.FilterOperators.equal, parseInt(this.getSelectedValue(), 10)));

            else

                $("#Grid1").ejGrid("model.query", new ej.Query());

            gridObj.refreshContent(true);

        }

    &lt;/script&gt;



The following output is displayed as a result of the above code example.



{ ![](Toolbar_images/Toolbar_img1.png) | markdownify }
{:.image }


