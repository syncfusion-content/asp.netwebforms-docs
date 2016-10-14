---
layout: post
title: Exporting | PivotChart | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotChart
documentation: ug
---

# Exporting

The PivotChart control can be exported to the following file formats.

* Excel
* Word
* PDF
* Image

The PivotChart control can be exported by invoking **“exportPivotChart”** method, with an appropriate export option as parameter.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    //...
     //If you want to render PivotChart in Client Mode.
    <ej:PivotChart ID="MyPivotChart1" runat="server" OnServerExcelExporting="PivotChart_ServerExcelExporting" ClientIDMode="Static">
        <DataSource>
        ....
        ....
        </DataSource>
     </ej:PivotChart>
     
     //If you want to render PivotChart in Server Mode.
    <ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" IsResponsive="true">
    <Size Width="950px" Height="460px"></Size>
    </ej:PivotChart>
    
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
        function exportBtnClick(args) {
            var chartObj = $('#MyPivotChart1').data("ejPivotChart");
            //If you render PivotChart in Client Mode, set the export option like below.
            chartObj.exportPivotChart("excelExport","fileName");
            
            //If you render PivotChart in Server Mode, set the export option like below.
            chartObj.exportPivotChart(ej.PivotChart.ExportOptions.Excel);;
            }
    </script>
</body>

</html>                                            

{% endhighlight %}

To achieve exporting in client mode, we need to add **"Syncfusion.EJ.Export"** dependency library into the application.

When PivotChart is rendered in Client Mode, a server side event method needs to be added in code behind file of the application and we need to import **"Syncfusion.EJ.Export"** namespace in the code behind file. 

{% highlight c# %}

protected void PivotChart_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotChartEventArgs e)
{
   System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer() { MaxJsonLength = Int32.MaxValue };
   PivotChartExcelExport pivotChartExcelExport = new PivotChartExcelExport();
   dynamic args = e.Arguments;
   Dictionary<string, string> chartParams = serializer.Deserialize<Dictionary<string, string>>(args["args"].ToString());
   pivotChartExcelExport.ExportToExcel(chartParams);
}
        
{% endhighlight %}

When PivotChart is rendered in Server Mode, a service method needs to be added in WCF/WebAPI for server side operations.

For WebAPI controller, the below method needs to be added.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
   string args = HttpContext.Current.Request.Form.GetValues(0)[0];
   string fileName = "Sample";
   htmlHelper.ExportPivotChart(args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For WCF service, the below method needs to be added.

{% highlight c# %}

public void Export(System.IO.Stream stream) {
   System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
   string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
   string fileName = "Sample";
   htmlHelper.ExportPivotChart(args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

## Excel Export

User can export contents of the PivotChart to Excel document for future archival, references and analysis purposes.

### Client Mode

To achieve Excel export, server side trigger event **"excelExport"** and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotChart ID="MyPivotChart1" runat="server" OnServerExcelExporting="PivotChart_ServerExcelExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotChart>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
          chartObj.exportPivotChart("excelExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotChart_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotChartEventArgs e)
{
   System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer() { MaxJsonLength = Int32.MaxValue };
   PivotChartExcelExport pivotChartExcelExport = new PivotChartExcelExport();
   dynamic args = e.Arguments;
   Dictionary<string, string> chartParams = serializer.Deserialize<Dictionary<string, string>>(args["args"].ToString());
   pivotChartExcelExport.ExportToExcel(chartParams);
}

{% endhighlight %}

### Server Mode

To achieve Excel export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base

For Excel export, **“ej.PivotChart.ExportOptions.Excel”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var chartObj = $('#MyPivotChart1').data("ejPivotChart");
    //Setting export option as Excel in the exportPivotChart method for ServerMode
    chartObj.exportPivotChart(ej.PivotChart.ExportOptions.Excel);
}

{% endhighlight %}  

![](Export_images/Export_ExcelClient.png)

## Word Export

User can export contents of the PivotChart to Word document for future archival, references and analysis purposes.

### Client Mode

To achieve Word export, server side trigger event **"wordExport"** and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotChart ID="MyPivotChart1" runat="server" OnServerWordExporting="PivotChart_ServerWordExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotChart>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
          chartObj.exportPivotChart("wordExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotChart_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.PivotChartEventArgs e)
{
     System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer() { MaxJsonLength = Int32.MaxValue };
     PivotChartWordExport pivotChartWordExport = new PivotChartWordExport();
     dynamic args = e.Arguments;
     Dictionary<string, string> chartParams = serializer.Deserialize<Dictionary<string, string>>(args["args"].ToString());
     pivotChartWordExport.ExportToWord(chartParams);
}

{% endhighlight %}

### Server Mode

 To achieve Word export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.DocIO.Base

For Word export, **“ej.PivotChart.ExportOptions.Word”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var chartObj = $('#MyPivotChart1').data("ejPivotChart");
    //Setting export option as Word in the exportPivotChart method
    chartObj.exportPivotChart(ej.PivotChart.ExportOptions.Word);
}

{% endhighlight %}

![](Export_images/Export_WordClient.png)

## PDF Export

User can export contents of the PivotChart to PDF document for future archival, references and analysis purposes.

### Client Mode

To achieve Word export, server side trigger event **"pdfExport"** and file name is sent as the parameter.

{% highlight html %}

    <ej:PivotChart ID="MyPivotChart1" runat="server" OnServerPDFExporting="PivotChart_ServerPDFExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotChart>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
          chartObj.exportPivotChart("pdfExport","fileName");
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotChart_ServerPDFExporting(object sender, Syncfusion.JavaScript.Web.PivotChartEventArgs e)
{
    System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer() { MaxJsonLength = Int32.MaxValue };
    PivotChartPDFExport pivotChartPDFExport = new PivotChartPDFExport();
    dynamic args = e.Arguments;
    Dictionary<string, string> chartParams = serializer.Deserialize<Dictionary<string, string>>(args["args"].ToString());
    pivotChartPDFExport.ExportToPDF(chartParams);
}

{% endhighlight %}

### Server Mode

To achieve PDF export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base

For PDF export, **“ej.PivotChart.ExportOptions.PDF”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args)
{
    var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
    //Setting export option as PDF in the exportPivotChart method
    chartObj.exportPivotChart(ej.PivotChart.ExportOptions.PDF);
}

{% endhighlight %} 

![](Export_images/Export_PDFClient.png)

## Image Export

User can export contents of the PivotChart to image format for future archival, references and analysis purposes. We can export PivotChart to the following image formats.

* PNG
* EMF
* JPG
* GIF
* BMP

###Client Mode

To achieve image export, server side trigger event **"imageExport"** ,**“ej.PivotChart.ExportOptions.PNG”** and file name is sent as the parameter.This is similar to other image formats.

{% highlight html %}

    <ej:PivotChart ID="MyPivotChart1" runat="server" OnServerImageExporting="PivotChart_ServerImageExporting" ClientIDMode="Static">
        <DataSource>
        </DataSource>
     </ej:PivotChart>
    <ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
       function exportBtnClick(args)
       {
          var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
          chartObj.exportPivotChart("imageExport","fileName",ej.PivotChart.ExportOptions.PNG);
       }
    </script>
    
{% endhighlight %}  

Following server side event method need to be added in code behind file of the application.

{% highlight c# %}

protected void PivotChart_ServerImageExporting(object sender, Syncfusion.JavaScript.Web.PivotChartEventArgs e)
{
   System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer() { MaxJsonLength = Int32.MaxValue };
   PivotChartImageExport pivotChartImageExport = new PivotChartImageExport();
   dynamic args = e.Arguments;
   Dictionary<string, string> chartParams = serializer.Deserialize<Dictionary<string, string>>(args["args"].ToString());
   pivotChartImageExport.ExportToImage(chartParams);
}

{% endhighlight %}

### Server Mode

To export PivotChart in PNG format, **“ej.PivotChart.ExportOptions.PNG”** enumeration value is sent as the parameter. This is similar to other image formats.

{% highlight js %}

function exportBtnClick(args)
{
    var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
    //Setting export option as PNG in the exportPivotChart method
    chartObj.exportPivotChart(ej.PivotChart.ExportOptions.PNG);
}

{% endhighlight %}  


![](Export_images/Export_PNGClient.png)

## Customize the export document name

### Client Mode

For customizing file name, we need to send file name as parameter to the **“exportPivotChart”**  method along with server side trigger event.

{% highlight js %}

function exportBtnClick(args)
{
    var chartObj = $('#MyPivotChart1').data("ejPivotChart ");
    chartObj.exportPivotChart("excelExport","fileName");
}
   
{% endhighlight %}
  
### Server Mode

For customizing name in WebAPI controller, below code snippet is used.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotChart(args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For customizing name in WCF Service, below code snippet is used.

{% highlight c# %}

public void Export(System.IO.Stream stream) {
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotChart(args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

