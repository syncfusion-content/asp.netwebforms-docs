---
layout: post
title: Paging
description: paging
platform: aspnet
control: Grid
documentation: ug
---

# Paging

Paging is a powerful technique in Grid that is used to navigate from one page to another. Using this pager, you can implement load on demand concept that loads only required data to Grid. To enable paging in Grid set AllowPaging as True at Grid Initialize.

## Default Paging

When the AllowPaging property is set as True, the properties in the pagesettings take the following default values.

* PageSize-12
* PageCount – 8
* CurrentPage-1

The following code example is for the Grid with default options.

{% highlight html %}

[ASP]

[aspx]

&lt;ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;



&lt;/ej:Grid&gt;



{% endhighlight  %}



The following output is displayed as a result of the above code example.



![](Paging_images/Paging_img1.png)
{:.image }


## External Paging

In this section, you can see how to use external paging. The following code example is for external paging.

{% highlight html %}

[ASP]

[aspx]

&lt;ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True"&gt; &lt;/ej:Grid&gt;



 &lt;div class="row"&gt;

        &lt;div class="col-md-3"&gt; goto &lt;/div&gt;

        &lt;div class="col-md-3"&gt;

          &lt;ej:NumericTextBox ID="goto" runat="server" Value="1" MinValue="1" MaxValue="10" ClientSideOnChange="pageChange" Width="100px" /&gt;

        &lt;/div&gt;

 &lt;/div&gt;



&lt;script type="text/javascript"&gt;

    function pageChange(args) {

        var gridobj = $("#OrdersGrid").data("ejGrid");

        gridobj.gotoPage(args.value);

    }

&lt;/script&gt;




{% endhighlight %}
The following output is displayed as a result of the above code example.



![](Paging_images/Paging_img2.png)
{:.image }


## Pager Templates

Pager Templates feature provide support to render a specific custom template to a Grid pager using EnableTemplates and Template properties of PageSettings. ShowDefaults property is used to show/hide default pager for Grid.

{% highlight html %}

[ASP]



[ASPX]



&lt;ej:Grid ID="FlatGrid" runat="server"&gt;

            &lt;PageSettings ShowDefaults="false" EnableTemplates="true" Template="#template" /&gt;

            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right” /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" /&gt;

                &lt;ej:Column Field="OrderDate" HeaderText="Order Date" TextAlign="Right" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;



    &lt;script type="text/x-jsrender" id="template"&gt;

        <a id="prev" value="Prev">Prev</a>

        &lt;input type="text"/&gt;

        &lt;input type="button" value="Go"/&gt;

        <a>Next</a>

    &lt;/script&gt; 

{% endhighlight %}
{% highlight c# %}
 [CS]



public partial class PrintGrid : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }

        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

            }

            this.FlatGrid.DataSource = order;

            this.FlatGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}





![](Paging_images/Paging_img3.png) 
{:.image }


## Methods

The following are the public methods of pager.

* gotoPage
* refreshPager

In this section, you can see how to use paging methods in Grid control. The following code example is for paging methods. 
{% highlight html %}
[ASP]

[aspx]

&lt;ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/"&gt;&lt;/DataManager&gt;



            &lt;PageSettings PageSize="5"&gt;&lt;/PageSettings&gt;

&lt;/ej:Grid&gt;



&lt;div class="row"&gt;

     &lt;div class="col-md-3"&gt; Allow Paging &lt;/div&gt;

     &lt;div class="col-md-3"&gt;

          &lt;ej:CheckBox ID="allowCheck" runat="server" Checked="True" ClientSideOnChange="onClick"&gt;&lt;/ej:CheckBox&gt;

     &lt;/div&gt;

 &lt;/div&gt;

 &lt;div class="row"&gt;

     &lt;div class="col-md-3"&gt; goto &lt;/div&gt;

     &lt;div class="col-md-3"&gt;

          &lt;ej:NumericTextBox ID="currentpage" runat="server" Value="1" MinValue="1" MaxValue="4" ClientSideOnChange="pageValChange" Width="100px" /&gt;

       &lt;/div&gt;

 &lt;/div&gt;

 &lt;div class="row"&gt;

     &lt;div class="col-md-3"&gt; Page Size &lt;/div&gt;

     &lt;div class="col-md-3"&gt;

        &lt;ej:NumericTextBox ID="pagesize" runat="server" Value="12" MinValue="1" MaxValue="20" ClientSideOnChange="sizeValChange" Width="100px" /&gt;

     &lt;/div&gt;

 &lt;/div&gt;

 &lt;div class="row"&gt;

   &lt;div class="col-md-3"&gt; Page Count &lt;/div&gt;

   &lt;div class="col-md-3"&gt;

       &lt;ej:NumericTextBox ID="pagecount" runat="server" Value="4" MinValue="1" MaxValue="4" ClientSideOnChange="countValChange" Width="100px" /&gt;

   &lt;/div&gt;

 &lt;/div&gt;



 &lt;script type="text/javascript"&gt;

 function onClick(args) {

            var model = $("#OrdersGrid").ejGrid("model");

            model.pageSettings.currentPage = 1;

            $("#currentpage").val(model.pageSettings.currentPage);

            $("#OrdersGrid").ejGrid({ allowPaging: args.isChecked });

            if (!args.isChecked)

                $("#currentpage, #pagecount, #pagesize") .ejNumericTextbox("disable");

            else

                $("#currentpage, #pagecount, #pagesize") .ejNumericTextbox("enable");

        }

 function sizeValChange(args) {

             var model = $("#OrdersGrid").ejGrid("model");

            var model1 = $("#OrdersGrid").ejGrid("getPager").ejPager("model");

            var newLastPage = Math.ceil(model.pageSettings.totalRecordsCount / args.value);

            if (model1.currentPage > newLastPage)

                $("#OrdersGrid").ejGrid("getPager").ejPager("goToPage", newLastPage);

            $("#OrdersGrid").ejGrid({ "pageSettings": { pageSize: parseInt(args.value) } });

            setPageValue(model1.totalPages);

        }

 function pageValChange(args) {

            var checkObj = $("#allowCheck").data("ejCheckBox");

            var ischecked = checkObj.option("checked");

            var model = $("#OrdersGrid").ejGrid("getPager").ejPager("model");

            if (ischecked && (parseInt(args.value) <= model.totalPages))

                $("#OrdersGrid").ejGrid("getPager").ejPager("goToPage", args.value);

        }

function countValChange(args) {

            var checkObj = $("#allowCheck").data("ejCheckBox");

            var ischecked = checkObj.option("checked");

            var model = $("#OrdersGrid").ejGrid("model");

            var pagermodel = $("#OrdersGrid").ejGrid("getPager").ejPager("model");

            if (ischecked && Math.ceil(model.pageSettings.totalRecordsCount / model.pageSettings.pageSize) >= parseInt(args.value))

                $("#OrdersGrid").ejGrid({ "pageSettings": { pageCount: parseInt(args.value) } });

            setPageValue(pagermodel.totalPages);

        }

function setPageValue(val) {

            $("#currentpage").ejNumericTextbox("model").maxValue = val;

            $("#pagecount").ejNumericTextbox("model").maxValue = val;

        }

&lt;/script&gt;
{% endhighlight  %}
{% highlight c# %}
[CS]

public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }




{% endhighlight %}




The following output is displayed as a result of the above code example.



![](Paging_images/Paging_img4.png) 
{:.image }


## Localization for paging

Localization is the process of customizing the user interface (UI) as locale-specific, inorder to display regional data. With this feature, data can be displayed in a language and culture specific to a particular country or region. The Asp.Net Grid control provides inherent support to localize its UI.

The following UIs are provided to localize based on culture. The default English localization UIs are as follows.



pagerInfo: "{0} of {1} pages ({2} items)",

firstPageTooltip: "Go to first page",

lastPageTooltip: "Go to last page",

nextPageTooltip: "Go to next page",

previousPageTooltip: "Go to previous page ",

nextPagerTooltip: "Go to next pager",

previousPagerTooltip: "Go to previous pager "



In this section, you can see how to use Globilzation in Grid pager. The following code example is for pager localization in German and Spanish. 

{% highlight html %}

[ASP]

[aspx]

&lt;ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" Locale="de-DE"&gt;

  &lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt; &lt;/DataManager&gt;



      &lt;/ej:Grid&gt;



 &lt;div class="row"&gt;

    &lt;div class="col-md-3"&gt; Selection Type &lt;/div&gt;

    &lt;div class="col-md-3"&gt;

        &lt;ej:DropDownList ID="language" runat="server" SelectedItemIndex="1" Width="120px" ClientSideOnChange="onChange"&gt;

            &lt;Items&gt;

              &lt;ej:DropDownListItem Text="English" Value="0" /&gt;

              &lt;ej:DropDownListItem Text="Deutsch" Value="1" /&gt;

              &lt;ej:DropDownListItem Text="Español" Value="2" /&gt;

            &lt;/Items&gt;

        &lt;/ej:DropDownList&gt;

     &lt;/div&gt;

 &lt;/div&gt;



&lt;script type="text/javascript"&gt;

   $(function () {

            $("#sampleProperties").ejPropertiesPanel();

        });

   function onChange(args) {

            if (args.itemId == 0)

                $("#OrdersGrid").ejGrid("model.locale", "en-US");

            else if (args.itemId == 1)

                $("#OrdersGrid").ejGrid("model.locale", "de-DE");

            else

                $("#OrdersGrid").ejGrid("model.locale", "es-ES");

        }

        ej.Grid.locale["es-ES"] = {

            EmptyRecord: "No hay registros que mostrar",

            GroupDropArea: "Arrastre un encabezado de columna aquí",

            DeleteOperationAlert: "No hay registros seleccionados para la operación de eliminación",

            EditOperationAlert: "No hay registros seleccionados para la operación de edición",

            SaveButton: "guardar",

            CancelButton: "cancelar",

            EditFormTitle: "Editar detalles de",

            GroupCaptionFormat: "artículos",

        };

 ej.Pager.locale["es-ES"] = {

            pagerInfo: "{0} de {1} páginas ({2} artículos)"

        };

        ej.Grid.locale["de-DE"]= {

            EmptyRecord: "Keine Aufzeichnungen angezeigt",

            GroupDropArea: "Ziehen Sie eine Spaltenüberschrift hier",

            DeleteOperationAlert: "Keine Einträge für Löschvorgang ausgewählt",

            EditOperationAlert: "Keine Einträge für Bearbeiten Betrieb ausgewählt",

            SaveButton: "Speichern",

            CancelButton: "stornieren",

            EditFormTitle: "Korrektur von",

            GroupCaptionFormat: "Beiträge",

        };

ej.Pager.locale["de-DE"] = {

            pagerInfo: "{0} von {1} Seiten ({2} Beiträge)"

        };

    &lt;/script&gt;


{% endhighlight %}


The following output is displayed as a result of the above code example.



![](Paging_images/Paging_img5.png)
{:.image }


