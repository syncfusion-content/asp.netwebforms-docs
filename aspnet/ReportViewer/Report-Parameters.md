---
layout: post
title: Report Parameters | ReportViewer | ASP.NET | Syncfusion
description: report parameters
platform: aspnet
control: ReportViewer
documentation: ug
---

# Report Parameters

The ReportViewer has support to add report parameters to ReportViewer at runtime. The ReportViewer has Parameters property that is the list of ReportParameter type to add collection of report parameters to it. You can add report parameters either through ReportViewer model when creating ReportViewer control or through Web API.

The following code example illustrates how to add ReportParameter at control creation.

{% highlight html %}

<ej:ReportViewer ID="viewer" runat="server" ReportServiceUrl="/api/RDLReport" ReportPath="InvoiceTemplate.rdl" ProcessingMode="Remote">
</ej:ReportViewer>

{% endhighlight %}

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
    viewer.Parameters = new List <ReportParameter>();
    viewer.Parameters.Add(new ReportParameter() {
        Name = "InvoiceID", 
        Labels = new List <string>() { "InvoiceID" }, 
        Values = new List <string>() { "10250" }
    });
}

{% endhighlight %}

The following code example illustrates how to add ReportParameter in Web API.

{% highlight c# %}

public class ReportsController: ApiController,IReportController
{
    /// <summary>
    /// Report Initialization method that is triggered when report begins to be processed.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnInitReportOptions(ReportViewerOptions reportOptions)
    {
        List <ReportParameter> parameters = new List <ReportParameter>();
        parameters.Add(new ReportParameter() { Name = "InvoiceID", Labels = new List <string>() { "InvoiceID" }, Values = new List <string>() { "10250" } });
        reportOptions.ReportModel.Parameters = parameters;
    }
}

{% endhighlight %}