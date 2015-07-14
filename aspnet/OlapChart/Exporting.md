---
layout: post
title: Exporting
description: exporting
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Exporting

The OLAP Chart control can be exported to the following formats:

* Excel
* Word
* PDF
* CSV
* PNG
* EMF
* GIF
* JPG
* BMP



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc"

        IsResponsive="true">&lt;/ej:OlapChart&gt;

&lt;ej:Button runat="server" ClientSideOnClick="ExportBtnClick" Text="Export"&gt;&lt;/ej:Button&gt;



function ExportBtnClick(args) {

    var chartObj = $('#OlapChart1').data("ejOlapChart");

    chartObj.exportOlapChart(ej.olap.OlapChart.ExportOptions.Excel);   

}



The Export type that is to be mentioned in the parameter takes any one of the following enumerated values.

* Excel
* Word
* PDF
* CSV
* PNG
* EMF
* GIF
* JPG
* BMP

The following code example of the service method needs to be added in-order to perform exporting in the OlapChart.

public void Export(System.IO.Stream stream)

{

    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);

    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd());

    OlapDataManager DataManager = new OlapDataManager(connectionString);

    string fileName = "OlapChart";

    htmlHelper.ExportOlapChart(DataManager, args, fileName,

    System.Web.HttpContext.Current.Response);

}



{ ![C:/Users/Narendhran Muthuvel/Desktop/Exported Screenshots/OlapChartExcelJS.png](Exporting_images/Exporting_img1.png) | markdownify }
{:.image }




{ ![C:/Users/Narendhran Muthuvel/Desktop/Exported Screenshots/OlapChartWordJS.png](Exporting_images/Exporting_img2.png) | markdownify }
{:.image }


{ ![C:/Users/Narendhran Muthuvel/Desktop/Exported Screenshots/OlapChartPdfJS.png](Exporting_images/Exporting_img3.png) | markdownify }
{:.image }




{ ![C:/Users/Narendhran Muthuvel/Desktop/Exported Screenshots/OlapChartImageJS.png](Exporting_images/Exporting_img4.png) | markdownify }
{:.image }


