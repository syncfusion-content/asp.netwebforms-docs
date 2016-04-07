---
layout: post
title: Paging | PivotGrid | ASP.NET | Syncfusion
description: paging
platform: aspnet
control: PivotGrid
documentation: ug
---

# Paging

I> This feature is applicable only for OLAP datasource only at Server Mode.

## Pager

Paging helps to improve the rendering performance of the PivotGrid control by breaking large amount of data into sections and displaying them.
 
In-order to initialize a "Pager", you need to initialize the widget using **"PivotPager"** method.

Inside the **"PivotPager"** method, the enumeration property `Mode` needs to be set to **"PivotPager.Mode.Both"** in-order to display both categorical pager and series pager. The other enumerations such as **"PivotPager.Mode.Categorical"** and **"PivotPager.Mode.Series"** will display only categorical pager and series pager respectively.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url = "../wcf/PagingService.svc" > </ej:PivotGrid>

 <ej:PivotPager ID="PivotPager1" runat="server" Mode="Both" TargetControlID="PivotGrid1"></ej:PivotPager>


{% endhighlight %}

Following are the navigation option available in Pager.

* Move First - Navigates to the first page.
* Move Previous - Navigates to the previous page from the current page.
* Move Next - Navigates to the next page from the current page.
* Move Last - Navigates to the last page. 
* Numeric Box - Navigates to the desired page by entering an appropriate numeric value.

![](Paging_images/paging.png)

## Virtual Scrolling

Virtual Scrolling is a technique that allows user to scroll vertically and horizontally the scroll bar to view the paged information. You can enable Virtual Scrolling option in PivotGrid by setting the `EnableVirtualScrolling` property to true.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PagingService.svc" EnableVirtualScrolling="true"></ej:PivotGrid>

{% endhighlight %}

![](Paging_images/virtual-scrolling.png) 

## Page Setting (Report)

The page setting for categorical and series axes are mandatorily needs to be done in OlapReport class by using the following properties.

* EnablePaging - Specifies a value indicating whether to enable or disable paging in PivotGrid control.
* PagerOptions.CategoricalPageSize - Specifies the number of categorical columns to be displayed within a page of the PivotGrid control.
* PagerOptions.SeriesPageSize - Specifies the number of series rows to be displayed within a page of the PivotGrid control.
* PagerOptions.CategoricalCurrentPage - Set the current page of the categorical axis in PivotGrid control.
* PagerOptions.SeriesCurrentPage - Set the current page of the series axis in PivotGrid control.

{% highlight C# %}

OlapReport olapReport = new OlapReport();
olapReport.EnablePaging = true;
olapReport.PagerOptions.SeriesPageSize = 4;
olapReport.PagerOptions.CategorialPageSize = 5;
olapReport.PagerOptions.CategorialCurrentPage = 1;
olapReport.PagerOptions.SeriesCurrentPage = 1;

DimensionElement dimensionElement = new DimensionElement() { Name = "Customer" };
dimensionElement.AddLevel("Customer", "Customer");
olapReport.CategoricalElements.Add(dimensionElement);

DimensionElement dimensionElementRow = new DimensionElement() { Name = "Customer", HierarchyName = "Customer" };
dimensionElementRow.AddLevel("Customer Geography", "Country");
olapReport.SeriesElements.Add(dimensionElementRow);

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
olapReport.CategoricalElements.Add(measureElementColumn);

{% endhighlight %}

