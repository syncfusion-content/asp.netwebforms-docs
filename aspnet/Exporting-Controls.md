---
layout: post
title: Exporting Multiple Syncfusion Controls | ASP.NET | Syncfusion
description: Exporting Multiple Syncfusion Controls
platform: ASP.NET
control: Common 
documentation: ug
---

#  Exporting Multiple Syncfusion Controls

We can export multiple Syncfusion controls like Grid, Chart, TreeGrid, etc., in a single document. 
This can be achieved by calling `ej.exportAll` method. exportAll method accepts two necessary parameters; one for routing URL (either to export Excel or PDF) and other for passing multiple controls ID’s as an array.  
In the server side we can handle exporting multiple control either Excel or PDF exporting by calling `ExportAll` method

The following code example describes the above behavior.

