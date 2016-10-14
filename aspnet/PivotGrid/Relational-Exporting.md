---
layout: post
title: Exporting | PivotGrid | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotGrid
documentation: ug
---

# Exporting

The PivotGrid control can be exported to the following file formats.

* Excel
* Word
* PDF
* CSV

The PivotGrid control can be exported by invoking **“exportPivotGrid”** method, with an appropriate export option as parameter.

## JSON Export

I> By default JSON export mode will be applied for server and client mode.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    //...
    //For PivotGrid in Client Mode.
    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerExcelExporting="PivotGrid_ServerExcelExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
    
    //For PivotGrid in Server Mode.
    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="../RelationalService" IsResponsive="true">
    </ej:PivotGrid>
    
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
        function exportBtnClick(args) {
            var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
            pGridObj.exportPivotGrid("excelExport","fileName");
        }
    </script>
</body>

</html>                                            

{% endhighlight %}

To achieve exporting in JSON mode, we need to add **"Syncfusion.EJ.Export"** dependency library into the application.

When PivotGrid is rendered, a server side event method needs to be added in code behind file of the application and we need to import **"Syncfusion.EJ.Export"** namespace in the code behind file. 

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

protected void PivotGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    dynamic args = e.Arguments;
    string fileName = "Sample";
    pGrid.ExportToExcel(fileName, args["args"].ToString(), HttpContext.Current.Response);
}
        
{% endhighlight %}

### Excel Export

User can export the contents of PivotGrid to an Excel document for future archival, references and analysis purposes.

To achieve Excel export, the **"excelExport"** server side event is triggered and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerExcelExporting="PivotGrid_ServerExcelExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("excelExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

protected void PivotGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    dynamic args = e.Arguments;
    string fileName = "Sample";
    pGrid.ExportToExcel(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

### Word Export

User can export the contents of PivotGrid to a Word document for future archival, references and analysis purposes.

To achieve Word export, the **"wordExport"** server side event is triggered and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerWordExporting="PivotGrid_ServerWordExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("wordExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

protected void PivotGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridWordExport pGrid = new PivotGridWordExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToWord(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

### PDF Export

User can export the contents of PivotGrid to a PDF document for future archival, references and analysis purposes.

To achieve Word export, the **"pdfExport"** server side event is triggered and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerPDFExporting="PivotGrid_ServerPDFExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("pdfExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

protected void PivotGrid_ServerPDFExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridPDFExport pGrid = new PivotGridPDFExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToPDF(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

### CSV Export

User can export the contents of PivotGrid to a CSV document for future archival, references and analysis purposes.

To achieve CSV export, the **"csvExport"** server side event is triggered and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerCSVExporting="PivotGrid_ServerCSVExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
          pGridObj.exportPivotGrid("csvExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

//...
using Syncfusion.EJ.Export;

protected void PivotGrid_ServerCSVExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridCSVExport pGrid = new PivotGridCSVExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToCSV(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

### Customize the export document name

For customizing file name, we need to send file name as parameter to the **“exportPivotGrid”**  method along with server side trigger event.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
    pGridObj.exportPivotGrid("excelExport","fileName");
}
 
{% endhighlight %}

## PivotEngine Export

I> This feature is applicable only at server mode operation.

In order to perform exporting with the use of PivotEngine available in server-side, the 'url' property obtained in the “BeforeExport” event is set to the value "server" as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    //...

    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="/RelationalService" IsResponsive="true">
        <ClientSideEvents  BeforeExport="Export"/>
    </ej:PivotGrid>
    
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
        function exportBtnClick(args) {
            var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
            pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);;
        }
        function Export(args) {
            args.url = "server";
        }
    </script>
</body>

</html>                                            

{% endhighlight %}

When PivotGrid is rendered in server mode, a service method needs to be added in WCF/WebAPI for server side operations.

For WebAPI controller, the below method needs to be added.

{% highlight c# %}

//...
using Syncfusion.Compression.Base;
using Syncfusion.XlsIO;
using Syncfusion.DocIO.Base;
using Syncfusion.Pdf.Base;

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export()
{
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
    htmlHelper.PopulateData(gridParams["currentReport"]);
    string fileName = "Sample";
    htmlHelper.ExportPivotGrid(ProductSales.GetSalesData(), args, fileName, HttpContext.Current.Response);
}

{% endhighlight %}

For WCF service, the below method needs to be added.

{% highlight c# %}

//...
using Syncfusion.Compression.Base;
using Syncfusion.XlsIO;
using Syncfusion.DocIO.Base;
using Syncfusion.Pdf.Base;

public void Export(System.IO.Stream stream)
{
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
    Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
    htmlHelper.PopulateData(gridParams["currentReport"]);
    string fileName = "Sample";
    htmlHelper.ExportPivotGrid(ProductSales.GetSalesData(), args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

### Excel Export

User can export the contents of PivotGrid to an Excel document for future archival, references and analysis purposes.

To achieve Excel export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base

For Excel export, **“ej.PivotGrid.ExportOptions.Excel”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
    //Setting export option as Excel in the exportPivotGrid method for ServerMode
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);
}

{% endhighlight %}  

### Word Export

User can export the contents of PivotGrid to a Word document for future archival, references and analysis purposes.

 To achieve Word export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.DocIO.Base

For Word export, **“ej.PivotGrid.ExportOptions.Word”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
    //Setting export option as Word in the exportPivotGrid method
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Word);
}

{% endhighlight %}

### PDF Export

User can export the contents of PivotGrid to a PDF document for future archival, references and analysis purposes.

To achieve PDF export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base

For PDF export, **“ej.PivotGrid.ExportOptions.PDF”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
    //Setting export option as PDF in the exportPivotGrid method
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.PDF);
}

{% endhighlight %} 

### CSV Export

User can export the contents of PivotGrid to a CSV document for future archival, references and analysis purposes.

For CSV export, **“ej.PivotGrid.ExportOptions.CSV”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
    //Setting export option as CSV in the exportPivotGrid method
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.CSV);
}

{% endhighlight %} 

### Customize the export document name

For customizing name in WebAPI controller, below code snippet is used.

{% highlight c# %}

//...
using Syncfusion.Compression.Base;
using Syncfusion.XlsIO;
using Syncfusion.DocIO.Base;
using Syncfusion.Pdf.Base;

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export()
{
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
    htmlHelper.PopulateData(gridParams["currentReport"]);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotGrid(ProductSales.GetSalesData(), args, fileName, HttpContext.Current.Response);
}

{% endhighlight %}

For customizing name in WCF Service, below code snippet is used.

{% highlight c# %}

//...
using Syncfusion.Compression.Base;
using Syncfusion.XlsIO;
using Syncfusion.DocIO.Base;
using Syncfusion.Pdf.Base;

public void Export(System.IO.Stream stream)
{
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
    Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
    htmlHelper.PopulateData(gridParams["currentReport"]);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotGrid(ProductSales.GetSalesData(), args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

The below screenshot shows the PivotGrid control exported to Excel document.

![](Exporting_images/ExportPivotExcel.png)

The below screenshot shows the PivotGrid control exported to Word document.

![](Exporting_images/ExportPivotWord.png)

The below screenshot shows the PivotGrid control exported to PDF document.

![](Exporting_images/ExportPivotPDF.png)

The below screenshot shows the PivotGrid control exported to CSV document.

![](Exporting_images/ExportPivotCSV.png)

