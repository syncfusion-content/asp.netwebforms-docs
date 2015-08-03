---
layout: post
title: Toolbar
description: toolbar 
platform: aspnet
control: Grid
documentation: ug
---

# Toolbar 

## Default buttons

Toolbar is one of the user interaction controls related with Grid. It is handy to use the Toolbar to trigger more actions. The default toolbar items created for Grid are:

* Add
* Edit
* Delete
* Update
* Cancel
* Search

If you want Toolbar items other than the above items, you can make it using customToolBarItems.

## Custom Toolbar action

Custom Toolbar is a key functionality, used to customize Toolbar elements. Here you can learn in detail about the Toolbar template and its actions in the Custom Toolbar category. In the following code example, ejDropDownList is used to filter records by category.

{% highlight html %}




  <script id="Refresh" type="text/x-jsrender">

        <select id="products">

            <option value="">All</option>

            <option value="2">Drinks</option>

            <option value="4">Dairy Products</option>

            <option value="3">Packages</option>

        </select>

    </script>



<ej:Grid ID="Grid1" runat="server" AllowScrolling="true">

        <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Products"></DataManager>

        <Columns>

            <ej:Column Field="ProductID" HeaderText="Product ID" IsPrimaryKey="True" TextAlign="Right" Width="100" />

            <ej:Column Field="ProductName" HeaderText="Product Name" Width="200" />

            <ej:Column Field="QuantityPerUnit" HeaderText="Quantity" TextAlign="Right" Width="100" />

            <ej:Column Field="UnitsOnOrder" HeaderText="UnitsOnOrder" Width="100" />

        </Columns>

        <ScrollSettings Height="300" Width="auto"></ScrollSettings>

        <ToolbarSettings ShowToolbar="true">

            <CustomToolbarItem>

                <ej:CustomToolbarItem TemplateID="#Refresh" />

            </CustomToolbarItem>

        </ToolbarSettings>

    </ej:Grid>
{% endhighlight  %}
{% highlight js %}



<script>



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

    </script>

{% endhighlight  %}

The following output is displayed as a result of the above code example.



![](Toolbar_images/Toolbar_img1.png)



