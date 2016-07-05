---
layout: post
title: ReportWriter | ReportWriter | ASP.NET | Syncfusion
description: export ssrs
platform: aspnet
control: ReportWriter
documentation: ug
---

## To Export SSRS Reports

The ReportWriter has options to export the SSRS reports. The following code example helps you to generate the SSRS report using ReportWriter.

Specify the `ReportPath`, `ReportServerUrl`, `ReportServerCredential`, `ReportProcessingMode` and `WriterFormat` properties for ReportWriter to generate report.

~~~csharp
HttpContext httpContext = System.Web.HttpContext.Current;
ReportWriter reportWriter = new ReportWriter();
reportWriter.ReportPath = "45db67a0-3fd6-4684-b03c-aa640a521c97";
reportWriter.ReportServerUrl = "http://reportserver.syncfusion.com:80/";
reportWriter.ReportingServer = new ReportingServerExt();
reportWriter.ReportServerCredential = new System.Net.NetworkCredential("guest", "demo");
reportWriter.ReportProcessingMode = ProcessingMode.Remote;
reportWriter.Save("GroupingAgg.doc", WriterFormat.Word, httpContext.Response);  
~~~