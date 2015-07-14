---
layout: post
title: Report-Controller
description: report controller
platform: aspnet
control: ReportViewer
documentation: ug
---

## Report Controller

The ReportViewer uses Web API services to process the report file, process the request from control, and to return the processed data to control. The Syncfusion.EJ.ReportViewer assembly has helper APIs to define the service actions and process the service requests. 

IReportController

The interface IReportController has the declaration of action methods that is defined in WebApi Controller for processing the RDL/RDLC files and for processing request from ReportViewer control. The IReportController has the following action methods declaration. 



_Table_ _1__: Report Controller methods_

<table>
<tr>
<td>
Methods</td><td>
Description</td></tr>
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
ReportHelper

The class ReportHelper contains helper methods that helps process Post/Get request from ReportViewer control and returns the response to ReportViewer control. The ReportHelper has the following methods. 

_Table_ _2__: Report Helper methods_

<table>
<tr>
<td>
Methods</td><td>
Description</td></tr>
<tr>
<td>
GetResource</td><td>
Returns the report resource for the requested key.</td></tr>
<tr>
<td>
ProcessReport</td><td>
Processes the report request and returns the result.</td></tr>
</table>


[C#]



public class ReportsController : ApiController, IReportController

    {

        /// &lt;summary&gt;

        /// Action (HttpGet) method for getting resource for report.

        /// &lt;/summary&gt;

        /// <param name="key">The unique key to get the required resource.&lt;/param&gt;

        /// <param name="resourceType">The type of the requested resource.&lt;/param&gt;

        /// <param name="isPrinting">If set to &lt;see langword="true"/&gt;, then the resource is generated for printing.&lt;/param&gt;

        /// <returns>The object data.&lt;/returns&gt;

        public object GetResource(string key, string resourceType, bool isPrinting)

        {

            //Returns the report resource for the requested key.

            return ReportHelper.GetResource(key, resourceType, isPrinting);

        }



        /// &lt;summary&gt;

        /// Report Initialization method that is triggered when report begin processed.

        /// &lt;/summary&gt;

        /// <param name="reportOptions">The ReportViewer options.&lt;/param&gt;

        public void OnInitReportOptions(ReportViewerOptions reportOptions)

        {

            throw new NotImplementedException();

        }



        /// &lt;summary&gt;

        /// Report loaded method that is triggered when report and sub report begins to be loaded.

        /// &lt;/summary&gt;

        /// <param name="reportOptions">The ReportViewer options.&lt;/param&gt;

        public void OnReportLoaded(ReportViewerOptions reportOptions)

        {

            throw new NotImplementedException();

        }



        /// &lt;summary&gt;

        /// Action (HttpPost) method for posting the request for report process. 

        /// &lt;/summary&gt;

        /// <param name="jsonData">The JSON data posted for processing report.&lt;/param&gt;

        /// <returns>The object data.&lt;/returns&gt;

        public object PostReportAction(Dictionary<string, object> jsonData)

        {

            //Processes the report request and returns the result.

            return ReportHelper.ProcessReport(jsonData, this);

        }

    }



