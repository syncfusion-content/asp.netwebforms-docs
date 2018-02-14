---
layout: post
title: Export Grid to target location without download prompt(Excel, Word or PDF) | Grid | ASP.NET Webforms | Syncfusion
description: Export Grid to target location without download prompt(Excel, Word or PDF)
platform: aspnet
control: Grid
documentation: ug
---

## Export Grid to target location without download prompt(Excel, Word or PDF)

In the Export method we have assigned the target location to save the exported file in the specified path. The target folder is placed using the Server.MapPath.

The following code example shows how to save the exported files in a target location.

{% tabs %}

 {% highlight html %}

<ej:Grid ID="FlatGrid" ClientIDMode="Static" runat="server" AllowPaging="True" OnServerExcelExporting="FlatGrid_ServerExcelExporting" 
OnServerWordExporting="FlatGrid_ServerWordExporting" OnServerPdfExporting="FlatGrid_ServerPdfExporting" >  
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
        
{% endhighlight %}

 {% highlight c# %}
 
public partial class GridExporting : System.Web.UI.Page
{ 
        protected void Page_Load(object sender, EventArgs e)
        {
            this.FlatGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            this.FlatGrid.DataBind();
        } 

        protected void FlatGrid_ServerExcelExporting(object sender, GridEventArgs e)
        {
            ExcelExport exp = new ExcelExport();
            string targetFolder = Server.MapPath("") + "\\New folder\\";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, false, false, "flat-lime", true, targetFolder);
        }

        protected void FlatGrid_ServerWordExporting(object sender, GridEventArgs e)
        {
            WordExport exp = new WordExport();
            string targetFolder = Server.MapPath("") + "\\New folder\\";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.docx", false, false, "flat-lime", true, targetFolder);
        }

        protected void FlatGrid_ServerPdfExporting(object sender, GridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            string targetFolder = Server.MapPath("") + "\\New folder\\";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.pdf", false, false, "flat-lime", true, targetFolder);
        }
}

{% endhighlight %}

{% endtabs %}
