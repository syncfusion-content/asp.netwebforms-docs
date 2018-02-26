---
layout: post
title: Enable Persistence with Grid widget for Syncfusion Essential ASP.NET
description: How to persist grid state across page refresh
platform: aspnet
control: Grid
documentation: ug
---

# Enable Persistence

Enable Persistence is to maintain the grid state in browser's [local storage](http://www.w3schools.com/html/html5_webstorage.asp#) even if browser refresh or move to next page. State persistence stores Grid's model object in local storage while defining `EnablePersistence` as true. 

I>  [localStorage](http://www.w3schools.com/html/html5_webstorage.asp#) is not supported below IE9 then grid state persistence technique is fallback to [cookie](http://www.w3schools.com/js/js_cookies.asp#).

## List of properties are not Persisted by default

The following properties are not included while maintaining Grid state in local storage to keep localStorage compact.

* Query
* IsEdit
* ToolbarClick
* QueryCellInfo
* MergeCellInfo
* CurrentViewData
* EnableAltRow
* EnableRTL 
* ContextClick 
* ContextOpen
* RowDataBound
* RowTemplate
* DetailsDataBound
* DetailsTemplate
* ChildGrid 
* SummaryRows 
* ToolbarSettings
* EditSettings
* AllowMultiSorting 
* EnableAutoSaveOnSelectionChange 
* Locale 
* AllowScrolling 
* AllowCellMerging
* AllowTextWrap 
* CssClass 
* DataSource 
* GroupSettings.EnableDropAreaAnimation 
* EnableRowHover 
* ShowSummary 
* AllowGrouping
* EnableHeaderHover 
* AllowKeyboardNavigation 
* ScrollSettings.FrozenRows 
* ScrollSettings.FrozenColumns 
* EnableTouch 
* EditSettings.RowPosition 
* EditSettings.ShowAddNewRow 
* ContextMenuSettings.EnableContextMenu

I> The Grid model properties can be maintained or prevented from being persisted using `addToPersist` and `ignoreOnPersist` methods.

## Accessing currently stored state

Persisted state can be accessed through local storage using corresponding key name. Key name is the combination of plugin name and control id.

{% highlight javascript %}

var gridStateString = window.localStorage.$ej$ejGridGrid; // grid state as string

var gridStateObject = JSON.parse(window.localStorage.$ej$ejGridGrid); //grid state as object

{% endhighlight %}


I> In the above example, "ejGrid" is plugin name and "Grid" is control id.



