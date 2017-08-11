---
layout: post
title: Key-Performance-Indicator-KPI
description: key performance indicator (KPI)
platform: aspnet
control: PivotClient
documentation: ug
---

# KPI

I> This feature is applicable for OLAP datasource only in Server Mode.

Key Performance Indicators (KPIs) are business metric that help to figure out the progress of an enterprise in meeting its business goals.

The different indicators available in KPI are:

* KPI Value: A physical measure or a calculated measure.
* KPI Goal: Defines the target for the measure.
* KPI Status: Evaluates the current status of the value compared to the goal.
* KPI Trend: Evaluate the current trend of the value compared to the goal.

The **“KpiElements”** class in OLAP Base library holds the KPI name and when its object is added to an OlapReport, you can view the resultant information in PivotClient.

### Client side property declaration

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server" EnableKPI="true" ClientIDMode="Static">
        //...
</ej:PivotClient>

{% endhighlight %}

### Framing OlapReport with KPI Elements

{% highlight c# %}

OlapReport olapReport = new OlapReport();
olapReport.Name = "KPI Report";
olapReport.CurrentCubeName = "Adventure Works";

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement {
    Name = "Gross Profit"
});

DimensionElement dimensionElementRow = new DimensionElement();
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

KpiElements kpiElement = new KpiElements();
kpiElement.Elements.Add(new KpiElement {
    Name = "Revenue", ShowKPIStatus = true, ShowKPIGoal = false, ShowKPITrend = true, ShowKPIValue = true
});

olapReport.CategoricalElements.Add(kpiElement);
olapReport.CategoricalElements.Add(measureElementColumn);
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight %}

![](KPI_images/KPI.png)

