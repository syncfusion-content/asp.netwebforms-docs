---
layout: post
title: Installation and Deployment | PDF | ASP.NET Webforms | Syncfusion
description: installation and deployment
platform: aspnet
control: PDF
documentation: ug
---

# Installation and Deployment

## System Requirements

To produce and manipulate PDF documents, the machine where Essential PDF runs on does not require Adobe Acrobat to be installed. Essential PDF is a PDF document creation engine. To view PDF documents produced by Essential PDF, the machine requires at least an Adobe Acrobat Reader.

### Prerequisites

The prerequisites details are listed as follows:



<table>
<tr>
<td>
.NET Framework versions</td><td>
<ul>
<li>.NET 4.5.1</li>
<li>.NET 4.5</li>
<li>.NET 4.0</li>
<li>.NET 3.5 SP1</li>
<li>.NET 2.0</li>
</ul>
</td></tr>
</table>

### Compatibility

 The compatibility details are listed as follows:



<table>
<tr>
<td>
Operating Systems</td><td>
<ul>
<li>Windows 8.1 (32 bit and 64 bit)</li>
<li>Windows 8 (32 bit and 64 bit)</li>
<li>Windows Server 2008 (32 bit and 64 bit)</li>
<li>Windows 7 (32 bit and 64 bit)</li>
<li>Windows Vista (32 bit and 64 bit)</li>
<li>Windows XP</li>
<li>Windows 2003</li>
</ul>
</td></tr>
</table>


## Deploy Essential PDF

### Assemblies


The following assemblies are to be referenced in your application for the usage of Essential PDF.

Full Trust Mode

In full trust mode, add references to the following assemblies corresponding to the platform:

PDF (Full-Trust) – WPF, Windows Forms, ASP. NET, MVC

* Syncfusion.Core.dll
* Syncfusion.Compression.Base.dll
* Syncfusion.GeckoHtmlRenderer.Base.dll
* Syncfusion.HTMLConverter.Base.dll
* Syncfusion.Pdf.Base.dll

PDF (Full - Trust) – Silverlight

* Syncfusion.Core.dll
* Syncfusion.Compression.Silverlight.dll
* Syncfusion.Pdf.Silverlight.dll

Medium/Partial Trust Mode

In medium/partial trust mode, add references to the following assemblies corresponding to the platform:

ASP.NET – PDF (Partial-Trust) – Web

* Syncfusion.Core.dll
* Syncfusion.Compression.Base.dll
* Syncfusion.Pdf.Web.dll

ASP.NET MVC – PDF (Partial-Trust) – MVC

* Syncfusion.Core.dll
* Syncfusion.Compression.Base.dll
* Syncfusion.Pdf.MVC.dll

### Referencing Syncfusion.Pdf.Base from a .Net project


To use a component in your application, you need to add a reference to it

1. In the application you created, open Solution Explorer. Right-click Reference folder and then click Add References.

2. Add the following assemblies as references in the application.

	* Syncfusion.Core.dll
	* Syncfusion.Compression.Base.dll
	* Syncfusion.Pdf.Base.dll
