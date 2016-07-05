---
layout: post
title: ReportWriter | ReportWriter | ASP.NET | Syncfusion
description: saving reports
platform: aspnet
control: ReportWriter
documentation: ug
---

# Saving Reports

Essential ReportWriter provides support for saving a report as a PDF, Word, Excel, PPT and HTML documents with the help of the class ReportWriter. The report elements such as Tablix, matrices, charts, gauges, shapes, and text boxes are supported in this feature. 

## Saving Report as PDF 

The report generated using the ReportDesigner can be exported as a PDF document using the following code.


~~~csharp
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save("Sample.pdf", WriterFormat.PDF);
~~~

~~~vbnet
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportpath, dataSources)
reportWriter.Save("Sample.pdf", WriterFormat.PDF)
~~~

![](ASP_Images/RDLExportPdf.png) 

## Saving Report as Excel 

The report generated using the ReportDesigner can be exported as an Excel document using the following code example. 

~~~csharp
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.xls", WriterFormat.Excel);
~~~
~~~vbnet
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.xls", WriterFormat.Excel)
~~~

![](ASP_Images/RDLExportExcel.png)

## Saving Report as Word 

The report generated using the ReportDesigner can also be exported as a Word document using the following code example.

~~~csharp
// Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.doc", WriterFormat.WORD);
~~~
~~~vbnet
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.doc", WriterFormat.WORD)
~~~

![](ASP_Images/RDLExportWord.png)

## Saving Report as an HTML 

The report generated using the ReportDesigner can be exported as an HTML document using the following code example. 

~~~csharp
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.html", WriterFormat.HTML);
~~~
~~~vbnet
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.html", WriterFormat.HTML)
~~~

![](ASP_Images/RDLExportHtml.png) 

## Saving Report as an PPT 

The report generated using the ReportDesigner can be exported as an PPT document using the following code example. 

~~~csharp
//Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
reportWriter.Save("Sample.ppt", WriterFormat.PPT);
~~~
~~~vbnet
'Instantiate the report writer with the parameter "ReportPath" and "ReportDataSource" Collection.
Dim reportWriter As New ReportWriter (reportPath, dataSources)
reportWriter.Save("Sample.ppt", WriterFormat.PPT)
~~~

![](ASP_Images/RDLExportPPT.png) 