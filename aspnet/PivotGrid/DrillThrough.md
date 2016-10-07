---
layout: post
title:  Drill Through | PivotGrid | ASP.NET | Syncfusion 
description:  drill through
platform: aspnet
control: PivotGrid
documentation: ug
---

# Drill Through

I> This feature is applicable only for OLAP data source.

Drill-through retrieves the raw items that are used to create a specified cell. To enable drill-through support, set [`EnableDrillThrough`] property to true. Raw items are obtained through the [`DrillThrough`] event, using which user can bind them to an external widget for precise view. 

N> Drill-through is supported in PivotGrid only when we configure and enable drill-through action at the Cube. 

![](DrillThrough_images/pivotgrid.png)

On clicking any value cell, the "Hierarchy Selector" dialog will be opened.  It consists of the dimensions which are associated with the measure of clicked value cell. In this example, the measure behind the respective cell is “Sales Amount” and the dimensions associated with this measure are alone displayed in the dialog.  

![](DrillThrough_images/hierarchy_selector.png)

Drag and drop the respective hierarchies and finally click “OK” button. Drill through MDX query will be framed and executed internally and provides back the raw items through "drillThrough" event. In this example, we have bound the raw items obtained to our ejGrid widget. Please refer the code sample and screen-shot below.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableDrillThrough="true" ClientIDMode="Static">
    //...
    <ClientSideEvents DrillThrough="drilledData" />
</ej:PivotGrid>

<script type="text/javascript">
    function drilledData(args) {
        gridData = JSON.parse(args.data);
        var dialogContent = ej.buildTag("div#" + this._id + "_tableDlg.tableDlg", ej.buildTag("div#Grid1")).attr("title", "Drill Through Information")[0].outerHTML; 
        $(dialogContent).appendTo("#" + this._id);
        $("#Grid1").ejGrid({
            dataSource: gridData,
            allowPaging: true,
            allowTextWrap: true,
            pageSettings: { pageSize: 8 }
        });
        this.element.find(".tableDlg").ejDialog({ width: "70%", content: "#" + this._id, enableResize: false });   
    }
</script>

{% endhighlight %}

When PivotGrid is rendered in server mode, below service methods need to be added in WCF/WebAPI for drill through operation.

For WebAPI controller, the below methods need to be added.

{% highlight c# %}

[System.Web.Http.ActionName("DrillthroughHierarchies")]
[System.Web.Http.HttpPost]
public string DrillthroughHierarchies(Dictionary<string, object> jsonResult)
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
    return htmlHelper.DrillthroughDataTable(DataManager, jsonResult["selectorValue"].ToString());
}  

{% endhighlight %}

For WCF service, the below methods need to be added. 

{% highlight c# %}

public string DrillthroughHierarchies(string currentReport, string layout, string cellPos)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return htmlHelper.DrillthroughHierarchies(DataManager, layout, cellPos);
}

public Dictionary<string, object> DrillThroughDataTable(string selectorValue, string currentReport)
{
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
    return htmlHelper.DrillthroughDataTable(DataManager, selectorValue);
}

{% endhighlight %}


![](DrillThrough_images/drill_data.png)

