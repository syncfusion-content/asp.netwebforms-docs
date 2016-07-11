---
layout: post
title: Exporting a Report as Various Document formats
description: How To export a report as PDF, Word, Excel, PPT and HTML documents?
platform: aspnet
control: ReportWriter
documentation: ug
---

# Export Types

Essential ReportWriter provides support for Exporting a report as a PDF, Word, Excel, PPT and HTML documents with the help of the class ReportWriter. The report elements such as Tablix, matrices, charts, gauges, shapes, and text boxes are supported in this feature. 

### Exporting Report as PDF

The report used in ReportWriter can be exported as PDF document using the following code.

~~~csharp

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save(Sample.pdf, WriterFormat.PDF);

~~~

![](ASP_Images/RDLExportPdf.png) 

### Exporting Report as Word

The report used in ReportWriter can be exported as Word document using the following code.

~~~csharp

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save(Sample.doc, WriterFormat.Word);

~~~

![](ASP_Images/RDLExportWord.png) 

### Exporting Report as Excel

The report used in ReportWriter can be exported as Excel document using the following code.

~~~csharp

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save(Sample.xls, WriterFormat.Excel);

~~~

![](ASP_Images/RDLExportExcel.png) 

### Exporting Report as HTML

The report used in ReportWriter can be exported as HTML document using the following code.

~~~csharp

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save(Sample.html, WriterFormat.HTML);

~~~

![](ASP_Images/RDLExportHtml.png) 

### Exporting Report as PPT

The report used in ReportWriter can be exported as PPT document using the following code.

~~~csharp

ReportWriter reportWriter = new ReportWriter(reportpath, dataSources);
reportWriter.Save(Sample.ppt, WriterFormat.PPT);

~~~

![](ASP_Images/RDLExportPPT.png) 