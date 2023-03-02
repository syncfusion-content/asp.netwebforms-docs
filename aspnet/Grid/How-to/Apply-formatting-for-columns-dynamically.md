---
layout: post
title: Apply formatting for columns | Grid | ASP.NET Webforms | Syncfusion
description: Learn here about how to apply formatting for columns dynamically in Syncfusion Essential ASP.NET WebForms Grid Control, its elements, and more.
platform: aspnet
control: Grid
documentation: ug
---

# Apply formatting for columns dynamically in ASP.NET WebForms Grid

Column format can be used dynamically to change data values format with the help of the public method. The following code example illustrates the Essential JavaScript with column formatting in public method.

{% highlight c# %}

var grid = $("#Grid").data("ejGrid");

var column = grid.getColumnByField("fieldName");

column.format = "{0:n2}";

grid.refreshContent(true);

 {% endhighlight %}

