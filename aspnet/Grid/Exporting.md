---
layout: post
title: Exporting | Grid | ASP.NET Webforms | Syncfusion
description: exporting
platform: aspnet
control: Grid
documentation: ug
---

# Exporting

Exporting feature provides support to export Grid data into excel, word and pdf files. The tool bar has ExcelExport, WordExport, PdfExport icons that are used to perform exporting. When you click the toolbar exporting icon, it internally invokes the export() public method of Grid object to make export. You can also invoke export() method manually to make export.

## ASP

In ASP, exporting is achieved by using Grid control server side method. Using Export() server method in Grid server side event, you can export the Grid into excel, pdf and word documents.

{% tabs %}

{% highlight html %}




<ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" OnServerWordExporting="FlatGrid_ServerWordExporting" OnServerPdfExporting="FlatGrid_ServerPdfExporting" OnServerExcelExporting="FlatGrid_ServerExcelExporting" AllowPaging="True">

            <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport,wordExport,pdfExport"></ToolbarSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" TextAlign="Right" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" />

            </Columns>

        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}




public partial class ExcelExporting : System.Web.UI.Page

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



        protected void FlatGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime");

        }



        protected void FlatGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            WordExport exp = new WordExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.docx", true, true, "flat-lime");

        }



        protected void FlatGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            PdfExport exp = new PdfExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.pdf", true, true, "flat-lime");

        }

    }
{% endhighlight  %}

{% endtabs %}

![](Exporting_images/Exporting_img1.png)



