---
layout: post
title: SSRS Configuration | ReportViewer | ASP.NET | Syncfusion
description: ssrs configuration
platform: aspnet
control: ReportViewer
documentation: ug
---

# SSRS Configuration

The ReportViewer has support to load RDL/RDLC reports from SSRS server. You have to set your SSRS server URL to ReportViewer’s ReportServiceUrl property and set the relative path of RDL/RDLC file in SSRS to ReportViewer’s ReportPath property. 

{% highlight html %}

<ej:ReportViewer ID="viewer" runat="server" ReportServiceUrl="/api/SSRSReport" ReportServerUrl="http://mvc.syncfusion.com/ReportServer"  ReportPath="/SSRSSamples2/Territory Sales New">
</ej:ReportViewer>

{% endhighlight %}

## Network Credentials for SSRS

The Network credentials can be given at WebAPI Controller to connect the SSRS server.

{% highlight c# %}

/// <summary>
/// Report Initialization method that is triggered when report begins to process.
/// </summary>
/// <param name="reportOptions">The ReportViewer options.</param>
public void OnInitReportOptions(ReportViewerOptions reportOptions)
{
    //Adds SSRS Server and Database Credentials here.
    reportOptions.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("ssrs", "RDLReport1");
    reportOptions.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("AdventureWorks", "ssrs1", "RDLReport1"));
}

{% endhighlight %}

N> DataSource credentials must be added to the ReportViewer for Shared DataSources that do not have credentials in the connection string and used in the SSRS Reports.

