---
layout: post
title: Paging | PivotGrid | ASP.NET | Syncfusion 
description: paging
platform: aspnet
control: PivotGrid
documentation: ug
---

# Paging

## Pager 

Paging helps to improve the rendering performance of the PivotGrid control by dividing large amount of data into sections and displaying one section at a time. You can enable Paging option in PivotGrid by setting the [`EnablePaging`] property to true. You can provide the page size and current page details for each axis in [`PagerOptions`] property.

In-order to initialize a **Pager**, first you need to define a **div** tag with an appropriate **id** attribute which acts as a container for the widget. Then you need to initialize the widget using **ejPivotPager** method.

Inside the **ejPivotPager** method, the enumeration property mode needs to be set to **ej.PivotPager.Mode.Both** in-order to display both categorical pager and series pager. The other enumerations such as **ej.PivotPager.Mode.Categorical** and **ej.PivotPager.Mode.Series** will display only categorical pager and series pager respectively.


{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnablePaging="true" runat="server" ClientIDMode="Static">
    <DataSource>
        //...
        <PagerOptions CategoricalPageSize="5" SeriesPageSize="5" CategoricalCurrentPage="1" SeriesCurrentPage="1" />
    </DataSource>
</ej:PivotGrid>

<ej:PivotPager ID="PivotPager1" runat="server" Mode="Both" TargetControlID="PivotGrid1"></ej:PivotPager>

{% endhighlight %}


Following are the navigation options available in Pager.

* Move First - Navigates to the first page.
* Move Last - Navigates to the last page. 
* Move Previous - Navigates to the previous page from the current page.
* Move Next - Navigates to the next page from the current page.
* Numeric Box - Navigates to the desired page by entering an appropriate page number in numeric value.

![](Paging_images/paging.png)


## Virtual Scrolling

Virtual Scrolling is a technique that allows user to view the PivotGrid information page by page with the use of vertical and horizontal scrollbar. You can enable Virtual Scrolling option in PivotGrid by setting the [`EnableVirtualScrolling`] property to true. You can provide the page size and current page details for each axis in [`PagerOptions`] property. 

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableVirtualScrolling="true" runat="server" ClientIDMode="Static">
    <DataSource>
        //...
        <PagerOptions CategoricalPageSize="5" SeriesPageSize="5" CategoricalCurrentPage="1" SeriesCurrentPage="1" />
    </DataSource>
</ej:PivotGrid>

{% endhighlight %}

![](Paging_images/virtual-scrolling.png)

## Page Settings

The properties associated to paging are:

* EnablePaging – This property is used to enable/disable paging in PivotClient control.
* PagerOptions.CategoricalPageSize - Specifies the number of categorical columns to be displayed within a page of the PivotClient control.
* PagerOptions.SeriesPageSize - Specifies the number of series rows to be displayed within a page of the PivotClient control.
* PagerOptions.CategoricalCurrentPage - Sets the current page of the categorical axis in PivotClient control.
* PagerOptions.SeriesCurrentPage - Sets the current page of the series axis in PivotClient control.

For client mode, page setting for categorical and series axes are mandatorily needed to be set in data source property by using the following properties.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnablePaging="true" runat="server" ClientIDMode="Static">
    <DataSource>
        //...
        <PagerOptions CategoricalPageSize="5" SeriesPageSize="5" CategoricalCurrentPage="1" SeriesCurrentPage="1" />
    </DataSource>
</ej:PivotGrid>

<ej:PivotPager ID="PivotPager1" runat="server" Mode="Both" TargetControlID="PivotGrid1"></ej:PivotPager>

{% endhighlight %}

For server mode, the page settings for categorical and series axes are done only through report object, created inside WebAPI or WCF file.

For Relational data source

{% highlight c# %}

PivotReport pivotReport = new PivotReport();
pivotReport.PagerOptions.SeriesPageSize = 4;
pivotReport.PagerOptions.CategoricalPageSize = 5;
pivotReport.PagerOptions.SeriesCurrentPage = 1;
pivotReport.PagerOptions.CategoricalCurrentPage = 1;

{% endhighlight %}

For OLAP data source

{% highlight c# %}

OlapReport olapReport = new OlapReport();
olapReport.CurrentCubeName = "Adventure Works";
olapReport.EnablePaging = true;
olapReport.PagerOptions.SeriesPageSize = 4;
olapReport.PagerOptions.CategoricalPageSize = 5;
olapReport.PagerOptions.CategoricalCurrentPage = 1;
olapReport.PagerOptions.SeriesCurrentPage = 1;

{% endhighlight %}