---
layout: post
title: Exporting | PivotChart | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotChart
documentation: ug
---

#Exporting

The PivotChart control can be exported to the following file formats.

* Excel
* Word
* PDF
* CSV
* Image

The additional script files required for exporting PivotChart are mentioned below:

* rgbcolor.js 
* StackBlur.js 
* canvg.js

These files are referred under the <head> tag in ASPX page.

{% highlight html %}

<head>
    //...
    <script type="text/javascript" src="http://gabelerner.github.io/canvg/rgbcolor.js"></script>
    <script type="text/javascript" src="http://gabelerner.github.io/canvg/StackBlur.js"></script>
    <script type="text/javascript" src="http://gabelerner.github.io/canvg/canvg.js"></script>

</head>
    
{% endhighlight %}

The PivotChart control can be exported by invoking **“exportPivotChart”** method, with an appropriate export option as parameter.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    //...
    <ej:PivotChart ID="PivotChart1" runat="server" Url="../wcf/PivotChartService.svc" IsResponsive="true">
    <Size Width="950px" Height="460px"></Size>
    </ej:PivotChart>
    <ej:Button runat="server" ClientSideOnClick="ExportBtnClick" Text="Export">
    </ej:Button>
    <script type="text/javascript">
        $(function() {
            $("#exportBtn").ejButton({
                click: "exportBtnClick"
            });
        });

        function exportBtnClick(args) {
            var chartObj = $('#PivotChart1').data("ejPivotChart");
                //provide export option type in the exportPivotChart method.
                chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.Excel);
            }
    </script>
</body>

</html>                                            

{% endhighlight %}

For WebAPI controller, the below method needs to be added to perform exporting.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = "Sample";
    htmlHelper.ExportPivotChart(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For WCF service, the below service method needs to be added to perform exporting.

{% highlight c# %}

public void Export(Stream stream) {
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = "Sample";
    htmlHelper.ExportPivotChart(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

##Excel Export
User can export contents of the PivotChart to Excel document for future archival, references and analysis purposes. To achieve Excel export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base

For Excel export, **“ej.olap.PivotChart.ExportOptions.Excel”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
        //set export option as Excel in the exportPivotChart method
        chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.Excel);
    }
{% endhighlight %}  

![](Export_images/Export_img1.png)

##Word Export
User can export contents of the PivotChart to Word document for future archival, references and analysis purposes. To achieve Word export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.DocIo.Base

For Word export, **“ej.olap.PivotChart.ExportOptions.Word”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
        //set export option as Word in the exportPivotChart method
        chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.Word);
    }

{% endhighlight %}

![](Export_images/Export_img2.png)

##CSV Export
User can export contents of the PivotChart to CSV document for future archival, references and analysis purposes.

For CSV export, **“ej.olap.PivotChart.ExportOptions.CSV”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
        //set export option as CSV in the exportPivotChart method
        chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.CSV);
    }

{% endhighlight %}

##PDF Export
User can export contents of the PivotChart to PDF document for future archival, references and analysis purposes. To achieve PDF export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base

For PDF export, **“ej.olap.PivotChart.ExportOptions.PDF”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
        //set export option as PDF in the exportPivotChart method
        chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.PDF);
    }

{% endhighlight %} 

![](Export_images/Export_img3.png)

##Image Export
User can export contents of the PivotChart to image format for future archival, references and analysis purposes. We can export PivotChart to the following image formats.

* PNG
* EMF
* JPG
* GIF
* BMP

For EMF export, **“ej.olap.PivotChart.ExportOptions.EMF”** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
    var chartObj = $('#PivotChart1').data("ejPivotChart ");
        //set export option as EMF in the exportPivotChart method
        chartObj.exportPivotChart(ej.olap.PivotChart.ExportOptions.EMF);
    }

{% endhighlight %}  

![](Export_images/Export_img4.png)

##Customize the export document name

The document name could be customized inside the method in WebAPI Controller. Following code sample illustrates the same.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = "File name is customized here";
    htmlHelper.ExportPivotChart(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For customizing name in WCF Service, below code snippet is used.

{% highlight c# %}

public void Export(System.IO.Stream stream) {
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotChart(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}
