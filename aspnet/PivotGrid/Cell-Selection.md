---
layout: post
title: Cell-Selection
description: cell selection
platform: aspnet
control: PivotGrid
documentation: ug
---

## Cell Selection

The PivotGrid control provides support to select specific ranges of value cells and display them in a format based on your requirement. The selection can be done through simple mouse down and drag operation. This functionality is not available by default. To enable this, you need to set the “enableCellSelection” property to “true”.

The following code example explains on how to enable cell selection in the PivotGrid control.

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

    &lt;ej:PivotGrid ID="PivotGrid1" IsResponsive="true" runat="server" url="../wcf/OLAPService.svc" ClientIDMode="Static" EnableCellSelection="true"&gt;

        &lt;clientsideevents cellselection="valueCellClick" /&gt;

    &lt;/ej:PivotGrid&gt;

&lt;/asp:Content&gt;



valueCellClick = function (evt) { 

// The event lets the user to perform required operation with the selected set of cells. The details of the selected range would be obtained in the parameter of the event.

    cellvalue = evt.JSONRecords;

    rowheaders = evt.rowHeader;

    colheaders = evt.columnHeader;

}

{ ![C:/Users/labuser/Desktop/cellselectionasp.net.png](Cell-Selection_images/Cell-Selection_img1.png) | markdownify }
{:.image }


{ ![C:/Users/labuser/Desktop/chart series.png](Cell-Selection_images/Cell-Selection_img2.png) | markdownify }
{:.image }






