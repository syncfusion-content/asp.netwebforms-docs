---
layout: post
title: Key-Performance-Indicator-KPI
description: key performance indicator (kpi)
platform: aspnet
control: PivotGrid
documentation: ug
---

# Key Performance Indicator (KPI)

KeyPerformanceIndicators are a collection of calculations associated with a measure group that evaluates business success. Typically, these calculations are a combination of multi-dimensional expressions (MDX) or calculated members. KPIs also have additional metadata that provide information about how grid applications display the results of the KPI calculations.

Note: This feature is applicable only for OLAP datasource.

The different types of available indicators are as follows:

* KPI Goal
* KPI Status
* KPI Trend
* KPI Value



 ![http://help.syncfusion.com/ug/js/ImagesExt/image49_164.jpg](Key-Performance-Indicator-KPI_images/Key-Performance-Indicator-KPI_img1.jpeg) 



 The following code example illustrates how to initialize KPI element within the OLAP Report:

{% highlight C# %}



   private OlapReport CreateOlapReport()

        {

         OlapReport olapReport = new OlapReport();

         olapReport.CurrentCubeName = "Adventure Works";



         DimensionElement dimensionElementColumn = new DimensionElement();

         dimensionElementColumn.Name = "Product";

         dimensionElementColumn.AddLevel("Product Categories", "Category");             

         dimensionElementColumn.Hierarchy.LevelElements["Category"].Add("Accessories");            dimensionElementColumn.Hierarchy.LevelElements["Category"].IncludeAvailableMembers = true;

         MeasureElements measureElementColumn = new MeasureElements();      

         measureElementColumn.Elements.Add(new MeasureElement { Name = "Gross Profit" });

         DimensionElement dimensionElementRow = new DimensionElement();           

         dimensionElementRow.Name = "Date";

         dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");



         KpiElements kpiElement = new KpiElements();

         kpiElement.Elements.Add(new KpiElement { Name = "Revenue", ShowKPIStatus = true, ShowKPIGoal = true, ShowKPITrend = true, ShowKPIValue = true });

         olapReport.CategoricalElements.Add(dimensionElementColumn);

         olapReport.CategoricalElements.Add(kpiElement);

         olapReport.CategoricalElements.Add(measureElementColumn);

         olapReport.SeriesElements.Add(dimensionElementRow);

         return olapReport;

        }


{% endhighlight %}
