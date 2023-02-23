---
layout: post
title: Apply formatting in ASP.NET Webforms Grid Control | Syncfusion
description: Learn here about apply formatting for columns dynamically in Syncfusion ASP.NET Webforms Grid Control, its elements, and more.
platform: aspnet
control: Grid
documentation: ug
---

# Apply formatting for columns in ASP.NET Webforms Grid

Column format can be used dynamically to change data values format with the help of the public method. The following code example illustrates the Essential JavaScript with column formatting in public method.

{% highlight c# %}

var grid = $("#Grid").data("ejGrid");

var column = grid.getColumnByField("fieldName");

column.format = "{0:n2}";

grid.refreshContent(true);

 {% endhighlight %}

