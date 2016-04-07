---
layout: post
title: Exporting | PivotGrid | ASP.NET | Syncfusion
description: exporting
platform: aspnet
control: PivotGrid
documentation: ug
---

# Exporting

The following table lists the exported file format for both Client and Server Mode of Relational datasource.

<table>
<tr>
<th>
Mode
</th>
<th>
File Formats
</th>
</tr>
<tr>
<td>
Client Mode
</td>
<td>
Excel
</td>
</tr>
<tr>
<td>
Server Mode
</td>
<td>
Excel, Word, PDF and CSV
</td>
</tr>
</table>

The PivotGrid control can be exported by invoking **"exportPivotGrid"** method, with an appropriate export option as parameter.

##Client Mode

For client side, Relational datasource contents can be exported only to Excel. The document can be saved from the browser to the local disk drive for later use.

To achieve Excel export, we need to add the following dependency library into the application.

* Syncfusion.EJ.Export

{% highlight js %}

<div class="row">
    <button id="btnExport" value="Excel" name="Excel" title="Excel Export">Export</button>
</div>

<ej:PivotGrid ID="PivotGrid1" runat="server" OnServerExcelExporting="PivotGrid_ServerExcelExporting" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
        </Columns>
        <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
        </Values>
    </DataSource>
    <ClientSideEvents Load="onLoad" />
</ej:PivotGrid>

<script type="text/javascript">
    $(function() {
        $("#btnExport").ejButton({
            roundedCorner: true,
            size: "small",
            click: "btnExportClick",
            type: ej.ButtonType.Button,
            contentType: "textandimage",
            prefixIcon: "e-excel-export"
        });
    });

    function onLoad(args) {
        args.model.dataSource.data = pivot_dataset;
    }

    function btnExportClick(args) {
        var gridObj = $('#PivotGrid1').data("ejPivotGrid");
        gridObj.exportPivotGrid("ExcelExport");
    }
</script>

{% endhighlight %}

Added the below method in code behind file to perform exporting
 
{% highlight c# %}

protected void PivotGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.PivotGridEventArgs e) {
    PivotGridExport pGrid = new PivotGridExport();
    dynamic args = e.Arguments;
    string fileName = "Sample";
    pGrid.ExportToExcel(fileName, args["args"].ToString(), HttpContext.Current.Response);
}

{% endhighlight %}


![](Exporting_images/RelationalClientMode.png)

##Server Mode

{% highlight html %}

<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

    <ej:button ID="Button1" runat="server" ClientSideOnClick="btnClick" Text="Export PivotGrid"></ej:button>

    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="../RelationalService"></ej:PivotGrid>

</asp:Content>

<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

    <script type="text/javascript">
        function btnClick(e) {
            var gridObj = $('#PivotGrid1').data("ejPivotGrid");
            gridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);

        }
    </script>

</asp:Content>

{% endhighlight %}

For WebAPI controller, the below method needs to be added to perform exporting.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = "Sample";
    htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For WCF service, the below service method needs to be added to perform exporting.

{% highlight c# %}

public void Export(System.IO.Stream stream) {
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);;
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = "Sample";
    htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

## Excel Export

User can export contents of the PivotGrid to Excel document for future archival, references and analysis purposes. To achieve Excel export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base

For Excel export, **"ej.PivotGrid.ExportOptions.Excel"** enumeration value is sent as the parameter.

{% highlight js %}

function exportBtnClick(args) {
   var gridObj = $('#PivotGrid1').data("ejPivotGrid");
   gridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Excel);
}

{% endhighlight %}  

![](Exporting_images/Sampleexcel.png)

## Word Export
User can export contents of the PivotGrid to Word document for future archival, references and analysis purposes. To achieve Word export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.DocIo.Base

For Word export, “ej.PivotGrid.ExportOptions.Word” enumeration value is sent as the parameter.  

{% highlight js %}

function exportBtnClick(args) {
   var gridObj = $('#PivotGrid1').data("ejPivotGrid");
   gridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.Word);
}

{% endhighlight %} 

![](Exporting_images/Sampleword.png)

## PDF Export
User can export contents of the PivotGrid to PDF document for future archival, references and analysis purposes. To achieve PDF export, we need to add the following dependency libraries into the application.

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base

For PDF export, **"ej.PivotGrid.ExportOptions.PDF"** enumeration value is sent as the parameter. 

{% highlight js %}

function exportBtnClick(args) {
   var gridObj = $('#PivotGrid1').data("ejPivotGrid");
   gridObj.exportPivotGrid(ej.PivotGrid.ExportOptions.PDF);
}

{% endhighlight %}  

![](Exporting_images/Samplepdf.png)


## Customize the export document name

The document name could be customized inside the method in WebAPI Controller. Following code sample illustrates the same.

{% highlight c# %}

[System.Web.Http.ActionName("Export")]
[System.Web.Http.HttpPost]
public void Export() {
    string args = HttpContext.Current.Request.Form.GetValues(0)[0];
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}

For customizing name in WCF Service, below code snippet is used.

{% highlight c# %}

public void Export(System.IO.Stream stream) {
    System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
    string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);;
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    string fileName = " File name is customized here ";
    htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
}

{% endhighlight %}


