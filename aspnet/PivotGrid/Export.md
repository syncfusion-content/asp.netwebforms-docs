---
layout: post
title: Export
description: export
platform: aspnet
control: PivotGrid
documentation: ug
---

## Export

> _Note:__This feature is applicable only for OLAP datasource._

The PivotGrid is exported from cell mode to a worksheet of an Excel Workbook. The Excel Workbook is saved from the browser to the local disk drive.

The following code example illustrates how to save the document to Excel via service.

For PivotGrid

[C#]

public void ExportOptions(Stream stream)

{

PivotGrid pivotGridHelper = new PivotGrid();

OlapDataManager DataManager=new OlapDataManager(connectionString);

pivotGridHelper.ExportToExcel(DataManager, newStreamReader(stream).ReadToEnd(), "Sample.xls",HttpContext.Current.Response);

}



[ASP.NET]

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

    &lt;ej:button ID="Button1" runat="server" ClientSideOnClick="btnClick" Text="Export PivotGrid"&gt;&lt;/ej:button&gt; 

    &lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc"&gt;&lt;/ej:PivotGrid&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

    &lt;script type="text/javascript"&gt;

        function btnClick(e) {

         pgridObj = $('#PivotGrid').data("ejPivotGrid");

         pgridObj.exportToExcel();

        }

    &lt;/script&gt;    

&lt;/asp:Content&gt;





{ ![Description: excelexport2](Export_images/Export_img1.png) | markdownify }
{:.image }


