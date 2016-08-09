---
layout: post
title: Exporting | PivotGrid | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotGrid
documentation: ug
---

#Exporting

The PivotGrid control can be exported to the following file formats.

* Excel
* Word
* PDF
* CSV

The PivotGrid control can be exported by invoking **“exportPivotGrid”** method, with an appropriate export option as parameter.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    //...
     //If you want to render PivotGrid in Client Mode.
    <ej:PivotGrid ID="PivotGrid1" runat="server" OnServerExcelExporting="PivotGrid_ServerExcelExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotGrid>
     
     //If you want to render PivotGrid in Server Mode.
    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="/RelationalService.svc" IsResponsive="true">
    </ej:PivotGrid>
    
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
        function exportBtnClick(args) {
            var pGridObj = $('#PivotGrid1').data("ejPivotGrid");
            //If you render PivotGrid in Client Mode, set the export option like below.
            pGridObj.exportPivotGrid("excelExport","fileName");
            
            //If you render PivotGrid in Server Mode, set the export option like below.
            pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);;
            }
    </script>
</body>

</html>                                            

{% endhighlight %}

To achieve exporting in client mode, we need to add **"Syncfusion.EJ.Export"** dependency library into the application.

When PivotGrid is rendered in Client Mode, a server side event method needs to be added in code behind file of the application and we need to import **"Syncfusion.EJ.Export"** namespace in the code behind file. 

{% highlight c# %}

protected void PivotGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    dynamic args = e.Arguments;
    string fileName = "Sample";
    pGrid.ExportToExcel(fileName, args["args"].ToString(), HttpContext.Current.Response);
}
        
{% endhighlight %}

When PivotGrid is rendered in Server Mode, a service method needs to be added in WCF/WebAPI for server side operations.

For WebAPI controller, the below method needs to be added.

{% highlight c# %}

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

##Excel Export

User can export contents of the PivotGrid to Excel document for future archival, references and analysis purposes.

###Client Mode

To achieve Excel export, server side trigger event **"excelExport"** and file name is sent as the parameter.

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
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
          pGridObj.exportPivotGrid("excelExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
    PivotGridExcelExport pGrid = new PivotGridExcelExport();
    dynamic args = e.Arguments;
    string fileName = "Sample";
    pGrid.ExportToExcel(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

###Server Mode

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

![](Exporting_images/ExportPivotExcel.png)

##Word Export
User can export contents of the PivotGrid to Word document for future archival, references and analysis purposes.

###Client Mode

To achieve Word export, server side trigger event **"wordExport"** and file name is sent as the parameter.

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
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
          pGridObj.exportPivotGrid("wordExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridWordExport pGrid = new PivotGridWordExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToWord(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

###Server Mode

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

![](Exporting_images/ExportPivotWord.png)

##PDF Export

User can export contents of the PivotGrid to PDF document for future archival, references and analysis purposes.

###Client Mode

To achieve Word export, server side trigger event **"pdfExport"** and file name is sent as the parameter.

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
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
          pGridObj.exportPivotGrid("pdfExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotGrid_ServerPDFExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridPDFExport pGrid = new PivotGridPDFExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToPDF(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

###Server Mode

To achieve PDF export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base

For PDF export, **“ej.PivotGrid.ExportOptions.PDF”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
    //Setting export option as PDF in the exportPivotGrid method
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.PDF);
}

{% endhighlight %} 

![](Exporting_images/ExportPivotPDF.png)

##CSV Export

User can export contents of the PivotGrid to CSV document for future archival, references and analysis purposes.

###Client Mode

To achieve CSV export, server side trigger event **"csvExport"** and file name is sent as the parameter.

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
          var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
          pGridObj.exportPivotGrid("csvExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotGrid_ServerCSVExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e)
{
     PivotGridCSVExport pGrid = new PivotGridCSVExport();
     dynamic args = e.Arguments;
     string fileName = "Sample";
     pGrid.ExportToCSV(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}

###Server Mode

For CSV export, **“ej.PivotGrid.ExportOptions.CSV”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
    //Setting export option as CSV in the exportPivotGrid method
    pGridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.CSV);
}

{% endhighlight %} 

![](Exporting_images/ExportPivotCSV.png)

##Customize the export document name

###Client Mode

For customizing file name, we need to send file name as parameter to the **“exportPivotGrid”**  method along with server side trigger event.

{% highlight js %}

function exportBtnClick(args)
{
    var pGridObj = $('#PivotGrid1').data("ejPivotGrid ");
    pGridObj.exportPivotGrid("excelExport","fileName");
}
 
{% endhighlight %}
    
###Server Mode

For customizing name in WebAPI controller, below code snippet is used.

{% highlight c# %}

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

