---
layout: post
title: Report Controller | ReportViewer | ASP.NET | Syncfusion
description: report controller
platform: aspnet
control: ReportViewer
documentation: ug
---

# Report Controller

The ReportViewer uses Web API services to process the report file, process the request from control, and to return the processed data to control. The Syncfusion.EJ.ReportViewer assembly has helper APIs to define the service actions and process the service requests. 

## IReportController

The interface IReportController has the declaration of action methods that is defined in WebApi Controller for processing the RDL/RDLC files and for processing request from ReportViewer control. The IReportController has the following action methods declaration. 

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Action (HttpGet) method for getting resource for report. </td></tr>
<tr>
<td>
PostReportAction</td><td>
Action (HttpPost) method for posting the request for report process. </td></tr>
<tr>
<td>
OnInitReportOptions</td><td>
Report initialization method that is triggered when report begins to be processed.</td></tr>
<tr>
<td>
OnReportLoaded</td><td>
Report loaded method that is triggered when report and sub report begin loading.</td></tr>
</table>

## ReportHelper

The class ReportHelper contains helper methods that helps process Post/Get request from ReportViewer control and returns the response to ReportViewer control. The ReportHelper has the following methods. 

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
GetResource</td><td>
Returns the report resource for the requested key.</td></tr>
<tr>
<td>
ProcessReport</td><td>
Processes the report request and returns the result.</td></tr>
</table>

{% highlight c# %}

public class ReportsController: ApiController,IReportController
{
    /// <summary>
    /// Action (HttpGet) method for getting resource for report.
    /// </summary>
    /// <param name="key">The unique key to get the required resource.</param>
    /// <param name="resourceType">The type of the requested resource.</param>
    /// <param name="isPrinting">If set to <see langword="true"/>, then the resource is generated for printing.</param>
    /// <returns>The object data.</returns>
    public object GetResource(string key, string resourceType, bool isPrinting)
    {
        //Returns the report resource for the requested key.
        return ReportHelper.GetResource(key, resourceType, isPrinting);
    }
    
    /// <summary>
    /// Report Initialization method that is triggered when report begin processed.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnInitReportOptions(ReportViewerOptions reportOptions)
    {
        //You can update report options here
    }
    
    /// <summary>
    /// Report loaded method that is triggered when report and sub report begins to be loaded.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnReportLoaded(ReportViewerOptions reportOptions)
    {
        //You can update report options here
    }
    
    /// <summary>
    /// Action (HttpPost) method for posting the request for report process. 
    /// </summary>
    /// <param name="jsonData">The JSON data posted for processing report.</param>
    /// <returns>The object data.</returns>
    public object PostReportAction(Dictionary < string, object > jsonData)
    {
        //Processes the report request and returns the result.
        return ReportHelper.ProcessReport(jsonData, this);
    }
}

{% endhighlight %}

