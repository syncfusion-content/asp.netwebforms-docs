---
layout: post
title:  Drill Through | PivotGrid | ASP.NET | Syncfusion
description:  This document explains that how to define drill through feature with respective to the modes in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Drill through

The drill-through retrieves the raw items that are used to create a specific cell. To enable drill-through support, set the `EnableDrillThrough` property to true. Raw items are obtained through the `DrillThrough` event, using which you can bind them to an external widget for a precise view.

## OLAP

N> The drill-through is supported in the pivot grid only when you configure and enable the drill-through action at the cube.

![Drill through support in ASP NET pivot grid control](DrillThrough_images/pivotgrid.png)

By clicking any value cell, the Drill Through Information dialog will be opened. It consists of a grid with data that is associated with the measure values of clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the values of the dimensions that are associated with this measure are alone displayed in the grid.

![Drill through data in ASP NET pivot grid control](DrillThrough_images/DrillThroughData.png)

By clicking the Hierarchy Selector that is displayed below the grid, the Hierarchy Selector dialog will be opened. It consists of dimensions that are associated with the measure of the clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the dimensions associated with this measure are alone displayed in the dialog.

![Hierarchy selector in ASP NET pivot grid control](DrillThrough_images/hierarchy_selector.png)

By dragging and dropping the respective hierarchies and clicking OK, the drill through MDX query will be framed and executed internally, and then it will provide the raw items back through the "drillThrough" event. In this example, the obtained raw items are bounded to the ejGrid widget. Refer the following code sample and screenshot:

## Client mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableDrillThrough="true" ClientIDMode="Static">
    <%--...--%>
    <ClientSideEvents DrillThrough="drilledData" />
</ej:PivotGrid>

<script type="text/javascript">
    function drilledData(args) {
        $(".e-dialog, .e-clientDialog, .e-tableDlg").remove();
        gridData = JSON.parse(args.data);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.e-tableDlg", $("<div id=\"Grid1\"></div>"))[0].outerHTML;
        var dialogFooter = ej.buildTag("div", ej.buildTag("button#btnOK.e-dialogBtnOK", "Hierarchy Selector")[0].outerHTML, { "float": "right", "margin": "-5px 0 6px" })[0].outerHTML
        ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent + dialogFooter, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        $("#btnOK").ejButton().css({ margin: "30px 0 20px 0" });
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".e-clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });
        var pivotGrid = $("#" + this._id).data("ejPivotGrid");
        $("#btnOK").click(function () {
            ej.Pivot.openHierarchySelector(pivotGrid);
        });
    }
</script>

{% endhighlight %}

## Server mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" url="/Olap" runat="server" EnableDrillThrough="true" ClientIDMode="Static">
    <%--...--%>
    <ClientSideEvents DrillThrough="drilledData" />
</ej:PivotGrid>

<script type="text/javascript">
    function drilledData(args) {
        $(".e-dialog, .e-clientDialog, .e-tableDlg").remove();
        gridData = ej.isNullOrUndefined(args.data.d) ? JSON.parse(args.data.DrillDataTable) : JSON.parse(args.data.d[1].Value);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.e-tableDlg", $("<div id=\"Grid1\"></div>"))[0].outerHTML;
        var dialogFooter = ej.buildTag("div", ej.buildTag("button#btnOK.e-dialogBtnOK", "Hierarchy Selector")[0].outerHTML, { "float": "right", "margin": "-5px 0 6px" })[0].outerHTML
        ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent + dialogFooter, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        $("#btnOK").ejButton().css({ margin: "30px 0 20px 0" });
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".e-clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });
        var pivotGrid = this;
        $("#btnOK").click(function () {
            $(".e-dialog, .e-clientDialog, .e-tableDlg").remove();
            if (pivotGrid.model.operationalMode == ej.PivotGrid.OperationalMode.ServerMode) {
                pivotGrid._waitingPopup.show()
                pivotGrid.doAjaxPost("POST", pivotGrid.model.url + "/" + pivotGrid.model.serviceMethodSettings.drillThroughHierarchies, JSON.stringify({ "currentReport": JSON.parse(pivotGrid.getOlapReport()).Report, "layout": pivotGrid.model.layout, "cellPos": "", "customObject": JSON.stringify(pivotGrid.model.customObject) }), function (args) {
                    ej.Pivot.openHierarchySelector(pivotGrid, args);
                })
            }
        });
    }
</script>

{% endhighlight %}

When the pivot grid is rendered in server mode, the below service methods should be added in the WCF/WebAPI for drill through operation.

For WebAPI controller, the following methods should be added:

{% highlight c# %}

[System.Web.Http.ActionName("DrillThroughHierarchies")]
[System.Web.Http.HttpPost]
public string DrillThroughHierarchies(Dictionary<string, object> jsonResult)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
    return htmlHelper.DrillthroughHierarchies(DataManager, jsonResult["layout"].ToString(), jsonResult["cellPos"].ToString());
}

[System.Web.Http.ActionName("DrillThroughDataTable")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> DrillThroughDataTable(Dictionary<string, object> jsonResult)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
    return htmlHelper.DrillthroughDataTable(DataManager, jsonResult["layout"].ToString(), jsonResult["cellPos"].ToString(), jsonResult["selector"].ToString());
}

{% endhighlight %}

For WCF service, the following methods should be added.

{% highlight c# %}

public string DrillThroughHierarchies(string currentReport, string layout, string cellPos)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return htmlHelper.DrillthroughHierarchies(DataManager, layout, cellPos);
}

public Dictionary<string, object> DrillThroughDataTable(string currentReport, string layout, string cellPos, string selector)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return htmlHelper.DrillthroughDataTable(DataManager, layout, cellPos, selector);
}

{% endhighlight %}


![Drill through data in ASP NET pivot grid OLAP server mode](DrillThrough_images/drill_data.png)

## Relational

To enable drill-through support, set the `EnableDrillThrough` property to true. Raw items are obtained through the `DrillThrough` event.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableGroupingBar="true" EnableDrillThrough="true" runat="server" ClientIDMode="Static">
    <%--...--%>
   <ClientSideEvents Load="onLoad" DrillThrough="drillData" />
</ej:PivotGrid>

<script type="text/javascript">
    function onLoad(args) {
        this.model.analysisMode = "pivot";
    }

    function drillData(args) {
    gridData = args.selectedData;
    var dialogContent = ej.buildTag("div#Grid", { })[0].outerHTML;
    ejDialog = ej.buildTag("div#clientDialog.e-clientDialog", dialogContent, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
    $(ejDialog).appendTo("#" + this._id);
    this.element.find(".e-clientDialog").ejDialog({ width: "auto", height: "300px", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });

    $("#Grid").ejGrid({
        dataSource: gridData,
        allowScrolling: true,
        scrollSettings: { width: "85%" },
        allowPaging: true,
        allowResizing: true,
        allowResizeToFit: true,
        pageSettings: {pageSize: 8}
    });
}
</script>

{% endhighlight %}

![Drill through data in ASP NET pivot grid relational mode](DrillThrough_images/DrillThroughRelational.png)