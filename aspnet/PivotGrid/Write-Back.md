---
layout: post
title: Write-Back | PivotGrid | ASP.NET | Syncfusion
description: write back
platform: aspnet
control: PivotGrid
documentation: ug
---


# Write-back

I> This feature is applicable only for the OLAP data source at server mode.

You can edit the values in the pivot grid and update a write enabled cube at the back-end (SSAS) dynamically at runtime.

N> Write-back is supported only for measures that use the **SUM** aggregation.

{% highlight js %}

<ej:PivotGrid ID="PivotGrid1" runat="server" url="/PivotGridService" EnableCellEditing="true">
</ej:PivotGrid>

{% endhighlight %}

{% highlight C# %}

public Dictionary < string, object > WriteBack(string action, string value, string rowUniqueName, string columnUniqueName, string currentReport) {
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.SetCurrentReport(Syncfusion.ASP NET.Olap.Utils.DeserializeOlapReport(currentReport));
    return htmlHelper.GetJsonData(action, DataManager, value, rowUniqueName, columnUniqueName);
}

{% endhighlight %}


![Write-back support in ASP NET pivot grid control](Write-Back_images/writeback.png)


