---
layout: post
title: ReportWriter | ReportWriter | ASP.NET | Syncfusion
description: export rdl
platform: aspnet
control: ReportWriter
documentation: ug
---

## To Export RDL Reports

The ReportWriter has options to export the RDL reports. The following code example helps you to export the RDL report using ReportWriter.

Specify the `ReportPath`, `ReportProcessingMode` and `WriterFormat` properties for ReportWriter to generate report.

~~~csharp   
string reportPath = @"..\ReportTemplate\GroupingAgg.rdl";
ReportWriter reportWriter = new ReportWriter(reportPath);
reportWriter.ReportProcessingMode = ProcessingMode.Remote;
reportWriter.Save("GroupingAgg.xls", WriterFormat.Excel);
~~~