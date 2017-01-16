---
layout: post
title:  Drill Through
description:  drill through
platform: aspnet
control: PivotClient
documentation: ug
---

# Drill Through

I> This feature is applicable only for OLAP data source.

Drill-through retrieves the raw items that are used to create a specified cell. To enable drill-through support, set [`enableDrillThrough`] property to true. Raw items are obtained through the [`drillThrough`] event, using which user can bind them to an external widget for precise view. 

N> Drill-through is supported in PivotGrid only when we configure and enable drill-through action at the Cube. 

![](DrillThrough_images/pivotclient.png)

On clicking any value cell, the "Drill Through Information" dialog will be opened. It consists of Grid with data which are associated with the measure values of the clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the values of the dimensions which are associated with this measure are alone displayed in the Grid. 

![](DrillThrough_images/DrillThroughData.png)

On clicking the "Hierarchy Selector" button which is displayed below the Grid, the "Hierarchy Selector" dialog will be opened. It consists of the dimensions which are associated with the measure of clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the dimensions associated with this measure are alone displayed in the dialog. 

![](DrillThrough_images/hierarchy_selector.png)

Drag and drop the respective hierarchies and finally click “OK” button. Drill through MDX query will be framed and executed internally and provides back the raw items through "drillThrough" event. In this example, we have bound the raw items obtained to our ejGrid widget. Please refer the code sample and screen-shot below.

## Client Mode

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server" EnableDrillThrough="true" ClientIDMode="Static">
        //...
        <ClientSideEvents DrillThrough="drilledData" />
</ej:PivotClient>

<script type="text/javascript">
    function drilledData(args) {
       $(".e-dialog, .clientDialog, .tableDlg").remove();
        gridData = JSON.parse(args.data);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.tableDlg", $("<div id=\"Grid1\"></div>"))[0].outerHTML;
        var dialogFooter = ej.buildTag("div", ej.buildTag("button#btnOK.dialogBtnOK", "Hierarchy Selector")[0].outerHTML, { "float": "right", "margin": "-5px 0 6px" })[0].outerHTML
        ejDialog = ej.buildTag("div#clientDialog.clientDialog", dialogContent + dialogFooter, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        $("#btnOK").ejButton().css({ margin: "30px 0 20px 0" });
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });
        var pivotClient = $("#" + this._id).data("ejPivotClient");
        $("#btnOK").click(function () {
            ej.Pivot.createHierarchySelector(pivotClient);
        });
    }
</script>

{% endhighlight %}

## Server Mode

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" Url="/Olap" runat="server" EnableDrillThrough="true" ClientIDMode="Static">
        //...
        <ClientSideEvents DrillThrough="drilledData" />
</ej:PivotClient>

<script type="text/javascript">
    function drilledData(args) {
        $(".e-dialog, .clientDialog, .tableDlg").remove();
        gridData = JSON.parse(args.data.d[1].Value);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.tableDlg", $("<div id=\"Grid1\"></div>"))[0].outerHTML;
        var dialogFooter = ej.buildTag("div", ej.buildTag("button#btnOK.dialogBtnOK", "Hierarchy Selector")[0].outerHTML, { "float": "right", "margin": "-5px 0 6px" })[0].outerHTML
        ejDialog = ej.buildTag("div#clientDialog.clientDialog", dialogContent + dialogFooter, { "opacity": "1" }).attr("title", "Drill Through Information")[0].outerHTML;
        $(ejDialog).appendTo("#" + this._id);
        $("#btnOK").ejButton().css({ margin: "30px 0 20px 0" });
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".clientDialog").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false, close: ej.proxy(ej.Pivot.closePreventPanel, this) });
        var pivotClient = this;
        $("#btnOK").click(function () {
            $(".e-dialog, .clientDialog, .tableDlg").remove();
            if (pivotClient.model.operationalMode == ej.PivotGrid.OperationalMode.ServerMode) {
                pivotClient._waitingPopup.show()
                pivotClient.doAjaxPost("POST", pivotClient.model.url + "/" + pivotClient.model.serviceMethodSettings.drillThroughHierarchies, JSON.stringify({ "currentReport": pivotClient.currentReport, "layout": pivotClient.model.layout, "cellPos": "", "customObject": JSON.stringify(pivotClient.model.customObject) }), function (args) {
                    ej.Pivot.createHierarchySelector(pivotClient, args);
                })
            }
        });
    }
</script>

{% endhighlight %}

When PivotGrid is rendered in server mode, below service methods need to be added in WCF/WebAPI for drill through operation.

For WebAPI controller, the below methods need to be added.

{% highlight c# %}

[System.Web.Http.ActionName("DrillThroughHierarchies")]
[System.Web.Http.HttpPost]
public string DrillThroughHierarchies(Dictionary<string, object> jsonResult)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);              
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
    return pivotClientHelper.DrillthroughHierarchies(DataManager, jsonResult["layout"].ToString(), jsonResult["cellPos"].ToString());
}

[System.Web.Http.ActionName("DrillThroughDataTable")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> DrillThroughDataTable(Dictionary<string, object> jsonResult)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
    return pivotClientHelper.DrillthroughDataTable(DataManager, jsonResult["layout"].ToString(), jsonResult["cellPos"].ToString(), jsonResult["selector"].ToString());
}  

{% endhighlight %}

For WCF service, the below methods need to be added. 

{% highlight c# %}

public string DrillThroughHierarchies(string currentReport, string layout, string cellPos)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return pivotClientHelper.DrillthroughHierarchies(DataManager, layout, cellPos);
}

public Dictionary<string, object> DrillThroughDataTable(string currentReport, string layout, string cellPos, string selector)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return pivotClientHelper.DrillthroughDataTable(DataManager, layout, cellPos, selector);
}

{% endhighlight %}


![](DrillThrough_images/drill_data.png)
