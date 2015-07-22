---
layout: post
title: Export
description: export
platform: aspnet
control: PivotGrid
documentation: ug
---

# Export

 Note: This feature is applicable only for OLAP datasource.

The PivotGrid is exported from cell mode to a worksheet of an Excel Workbook. The Excel Workbook is saved from the browser to the local disk drive.

The following code example illustrates how to save the document to Excel via service.

For PivotGrid
{% highlight C# %}



public void ExportOptions(Stream stream)

{

PivotGrid pivotGridHelper = new PivotGrid();

OlapDataManager DataManager=new OlapDataManager(connectionString);

pivotGridHelper.ExportToExcel(DataManager, newStreamReader(stream).ReadToEnd(), "Sample.xls",HttpContext.Current.Response);

}
{% endhighlight %}

{% highlight html %}


<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

    <ej:button ID="Button1" runat="server" ClientSideOnClick="btnClick" Text="Export PivotGrid"></ej:button> 

    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc"></ej:PivotGrid>

</asp:Content>

<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

    <script type="text/javascript">

        function btnClick(e) {

         pgridObj = $('#PivotGrid').data("ejPivotGrid");

         pgridObj.exportToExcel();

        }

    </script>    

</asp:Content>

{% endhighlight %}



 ![Description: excelexport2](Export_images/Export_img1.png) 



