---
layout: post
title: Server side events | PivotChart | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: PivotChart
documentation: ug
---

## Server-side: Event Arguments

This section explains in detail about the various server-side events available in the control and the arguments that are passed to server-side. 

The **sender** parameter of all server-side events returns the PivotChart model details. The **Syncfusion.JavaScript.Web.PivotChartEventArgs** arguments provide information specific to this event.

The various server-side events and the arguments corresponding to the events are as follows:

## OnDrillSuccess

The **OnDrillSuccess** event is triggered while performing drill operation on Chart series. The details of the drilled series information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of drilled series information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnDrillSuccess="PivotChart1_DrillSuccess"></ej:PivotChart>

{% endhighlight %}

 {% highlight c# %}

protected void PivotChart1_DrillSuccess(object sender, PivotChartEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}
    
{% endtabs %}
	
### OnPointRegionClick

The **OnPointRegionClick** event is triggered when Chart series is clicked. The details of the clicked Chart series information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked Chart series information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnPointRegionClick="PivotChart1_PointRegionClick"></ej:PivotChart>

{% endhighlight %}

{% highlight c# %}

protected void PivotChart1_PointRegionClick(object sender, PivotChartEventArgs e)
{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}

## OnServerExcelExporting

The **OnServerExcelExporting** event is triggered when a request is made to export the control to Excel document. The PivotChart model details can be obtained from server-side, which is explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotChart information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnServerExcelExporting="PivotChart1_ServerExcelExporting"></ej:PivotChart>

{% endhighlight %}

{% highlight c# %}

protected void PivotChart1_ServerExcelExporting(object sender, PivotChartEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnServerPDFExporting

The **OnServerPDFExporting** event is triggered when a request is made to export the control to PDF file. The PivotChart model details can be obtained from server-side, which is explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotChart information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnServerPDFExporting="PivotChart1_ServerPDFExporting"></ej:PivotChart>

{% endhighlight %}

 {% highlight c# %}

protected void PivotChart1_ServerPDFExporting(object sender, PivotChartEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}
   
## OnServerImageExporting

The **OnServerImageExporting** event is triggered when a request is made to export the control to an image format. The PivotChart model details can be obtained from server-side, which is explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotChart information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnServerImageExporting="PivotChart1_ServerImageExporting"></ej:PivotChart>

{% endhighlight %}

 {% highlight c# %}

protected void PivotChart1_ServerImageExporting(object sender, PivotChartEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}
   
## OnServerWordExporting

The **OnServerWordExporting** event is triggered when a request is made to export the control to Word document. The PivotChart model details can be obtained from server-side, which is explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotChart information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotChart ID="PivotChart1" runat="server" OnServerWordExporting="PivotChart1_ServerWordExporting"></ej:PivotChart>

{% endhighlight %}

 {% highlight c# %}

protected void PivotChart1_ServerWordExporting(object sender, PivotChartEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}
