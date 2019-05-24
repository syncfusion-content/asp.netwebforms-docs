---
layout: post
title: pivotGrid elements | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to customize cells with an interactive way in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Pivot grid: Elements

## Hyperlink
The pivot grid control supports hyperlink option to link data for each individual cell. The hyperlink can be enabled separately for row header, column header, value cell, and summary cell. Following are the respective properties:

* **EnableColumnHeaderHyperlink**: Enables hyperlink for column headers.
* **EnableRowHeaderHyperlink**: Enables hyperlink for row headers.
* **EnableSummaryCellHyperlink**: Enables hyperlink for a summary cell.
* **EnableValueCellHyperlink**: Enables hyperlink for a value cell.

Also, hyperlink option provides separate events for row header, column header, and value and summary cells as mentioned below:

* **ColumnHeaderHyperlinkClick**: Returns column header information through the event by clicking the hyperlink.
* **RowHeaderHyperlinkClick**: Returns row header information through the event by clicking the hyperlink.
* **SummaryCellHyperlinkClick**: Returns summary cell information through the event by clicking the hyperlink.
* **ValueCellHyperlinkClick**: Returns value cell information through the event by clicking the hyperlink.


{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
        <HyperlinkSettings EnableColumnHeaderHyperlink="true" EnableValueCellHyperlink="true" EnableRowHeaderHyperlink="true" EnableSummaryCellHyperlink="true" />
        <ClientSideEvents ValueCellHyperlinkClick="CellClickEvent" RowHeaderHyperlinkClick="CellClickEvent" ColumnHeaderHyperlinkClick="CellClickEvent" SummaryCellHyperlinkClick="CellClickEvent" />
</ej:PivotGrid>

<script type="text/javascript">
    CellClickEvent = function (evt) {
        alert("Cell Click event is fired");
    }
</script>

{% endhighlight %}

![Hyperlink in ASP NET pivot grid control](PivotGrid-Elements_images/hyperlink.png)

## Selection
You can select a particular range of value cells from the pivot grid and manipulate/display them. The cell selection is applicable only for value cells and you can enable this functionality by setting the `EnableCellSelection` property to true.

The **"CellSelection"** event will be triggered as soon as the selection process is over, i.e., the event will be triggered when you release the mouse left-click. The event argument contains a collection of JSON records, and header values contains information about the selected cells.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableCellSelection="true" >
    <ClientSideEvents CellSelection="valueCellClick"/>
</ej:PivotGrid>

<script type="text/javascript">
    valueCellClick = function (evt) {
        // The event lets you to perform required operation with the selected set of cells. The details of the selected range can be obtained in the parameter of the event.
        cellvalue = evt.JSONRecords;
        rowheaders = evt.rowHeader;
        colheaders = evt.columnHeader;
    }
</script>

{% endhighlight %}

![Cell selection in ASP NET pivot grid control](PivotGrid-Elements_images/cellselection.png)

## Cell context
The cell context allows you to perform any custom operation by right-clicking the cell. For example, you can create and display the context menu by right-clicking the cell.

The cell context is enabled by setting the `EnableCellContext` property to true. The **"CellContext"** event will be raised as soon as the right-click is done to provide cell information through the event argument.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableCellContext="true">
    <clientsideevents CellContext="cell_RightClick" />
</ej:PivotGrid>

<script type="text/javascript">
    cell_RightClick = function (evt) {
        //Write your Cell Context code here
    }
</script>

{% endhighlight %}

## Conditional formatting
The conditional formatting allows you to highlight the particular cells with certain color, font-style, font-family etc., based on the conditions they have met. It is enabled by setting the `EnableConditionalFormatting` property to true, and the formatting dialog will be launched when the **"createConditionalDialog"** method is invoked.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableConditionalFormatting="true">
    //...
</ej:PivotGrid>

<ej:Button ClientSideOnClick="btnClick" runat="server" Text="Conditional"></ej:Button>

<script type="text/javascript">
    function btnClick(e) {
        var pivotGridObj = $('#PivotGrid1').data("ejPivotGrid");
        if (pivotGridObj.model.enableConditionalFormatting) {
            pivotGridObj.createConditionalDialog();
        }
    }
</script>

{% endhighlight %}

![Conditional formatting dialog in ASP NET pivot grid control](PivotGrid-Elements_images/FormatDialog.png)

![ASP NET pivot grid control with conditional formatting](PivotGrid-Elements_images/FormattedGrid.png)

### Export

You can export the pivot grid with highlighted particular cells along with its formatting styles.

Limitations for Word:

The following border styles are not supported:

* Solid
* Groove
* Ridge

Limitations for PDF:

Border styles are not applicable.

Limitations for Excel:

The following border styles are alone supported:

* Dashed
* Dotted
* Double

Also, the border size is not supported.

![Excel exporting with conditional formatting in ASP NET pivot grid control](PivotGrid-Elements_images/conditional_export.png)

