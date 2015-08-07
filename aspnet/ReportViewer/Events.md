---
layout: post
title: Events
description: events
platform: aspnet
control: ReportViewer
documentation: ug
---

# Events

The ReportViewer has the following client-side events support to listen to the control action.

_Table_ _3_: _Client-Side events_

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
destroy</td><td>
Fires when the ReportViewer is destroyed.</td></tr>
<tr>
<td>
drillThrough</td><td>
Fires during drill through action done in report and event can be cancelled.</td></tr>
<tr>
<td>
renderingBegin</td><td>
Fires before report rendering is completed.</td></tr>
<tr>
<td>
renderingComplete</td><td>
Report loaded method that is triggered when report and sub report begin loading.</td></tr>
<tr>
<td>
reportError</td><td>
Fires when any error occurs while rendering the report and event can be cancelled.</td></tr>
<tr>
<td>
reportLoaded</td><td>
Fires when the report is loaded.</td></tr>
</table>






{% highlight html %}

[EJWEB]

        <ej:ReportViewer ID="viewer" runat="server" ReportServiceUrl="/api/RDLCReport" ReportPath="DatabindingRemote.rdlc" ProcessingMode="Local" OnClientReportLoaded="reportLoaded">

        </ej:ReportViewer>
		
{% endhighlight %}

{% highlight js %}


<script type="text/javascript">

        function reportLoaded(senderObj) {

                $.ajax({

                    type: "POST",

                    contentType: "application/json; charset=utf-8",

                    url: '../wcf/Reportservice.svc/GetOrderDetails',

                    dataType: "json",

                    processData: false, 

                    crossDomain: true,

                    async: false,

                    timeout: 5000,

                    success: function (result) {

                        reportdata = result.d;  

                        var dataManger = ej.DataManager(reportdata);

                        var query = ej.Query().select("OrderID", "CustomerID", "EmployeeID", "Freight", "ShipCity", "ShipCountry");

                        reportResult = dataManger.executeLocal(query);

                        var reportModel = $("#viewer").data('ejReportViewer');

                        reportModel.model.dataSources = [{ value: reportResult, name: "remote" }];

                    },

                    error: function (result) {

                        alert(result);

                    }

            });

           }

    </script>

{% endhighlight %}









