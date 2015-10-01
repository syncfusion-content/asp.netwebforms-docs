---
layout: post
title: Exporting | PivotGrid | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotGrid
documentation: ug
---

# Exporting

The PivotGrid control can be exported to the following formats:

* Excel (Cell Mode)
* Word
* PDF
* CSV

{% highlight html %}
<ej:PivotGrid ID="PivotGrid1" runat="server" IsResponsive="true"

              Url="../wcf/OLAPService.svc" ClientIDMode="Static"></ej:PivotGrid>

<ej:Button runat="server" ClientSideOnClick="exportBtnClick" Text="Export"></ej:Button>

function exportBtnClick(args) {

    var gridObj = $('#PivotGrid1').data("ejPivotGrid");

    gridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);

}
{% endhighlight %}

The Export type that is to be mentioned in the parameter takes any one of the following enumerated values such as Excel, Word, PDF and CSV.

The following code example of the service method needs to be added in-order to perform exporting in the PivotGrid.

{% highlight C# %}
public void Export(System.IO.Stream stream)

{

    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);

    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd());

    OlapDataManager DataManager = new OlapDataManager(connectionString);

    string fileName = "PivotGrid";

    htmlHelper.ExportPivotGrid(DataManager, args, fileName,

    System.Web.HttpContext.Current.Response);

}
{% endhighlight %}

![](Exporting_images/Exporting_img1.png) 

Exported PivotGrid in Excel
{:.caption}

![](Exporting_images/Exporting_img2.png) 

Exported PivotGrid in Word
{:.caption}

![](Exporting_images/Exporting_img3.png)

Exported PivotGrid in PDF
{:.caption}

![](Exporting_images/Exporting_img4.png) 

Exported PivotGrid in CSV
{:.caption}

