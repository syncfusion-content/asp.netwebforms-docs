---
layout: post
title: Server side events | PivotClient | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: PivotClient
documentation: ug
---

## Server side event arguments in ASP PivotClient

This section explains in detail about the various server-side events available in the control and the arguments that are obtained server-side. 

The **sender** parameter of all the server-side events returns the PivotClient model details. The **Syncfusion.JavaScript.Web.PivotClientEventArgs** arguments provide information specific to this event.

The various server-side events and the arguments corresponding to the events are as follows:

## OnGridDrillSuccess

The **OnGridDrillSuccess** event is triggered while performing expand/collapse operation on row/columns headers. The details of the drilled cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of drilled cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" OnGridDrillSuccess="PivotClient1_GridDrillSuccess"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_GridDrillSuccess(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}  
  
{% endtabs %}

## OnChartDrillSuccess

The **OnChartDrillSuccess** event is triggered while performing drill operation on Chart series. The details of the drilled series information can be obtained at server-side, as explained in the following table.

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

<ej:PivotClient ID="PivotClient1" runat="server" OnChartDrillSuccess="PivotClient1_ChartDrillSuccess"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_ChartDrillSuccess(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}
    
{% endtabs %}

## OnTreeMapDrillSuccess

The **OnTreeMapDrillSuccess** event is triggered while performing drill operation on treemap. The details of the drilled tile information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of drilled tile series information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" OnTreeMapDrillSuccess="PivotClient1_TreeMapDrillSuccess"></ej:PivotClient>

{% endhighlight %}

{% highlight c# %}

protected void PivotClient1_TreeMapDrillSuccess(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotTreeMap.
}
    
{% endhighlight %}
    
{% endtabs %}
	
### OnValueCellHyperlinkClick

The **OnValueCellHyperlinkClick** event is triggered when any of the value cell is clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableValueCellHyperlink="true" OnValueCellHyperlinkClick="PivotClient1_ValueCellHyperlinkClick"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_ValueCellHyperlinkClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnRowHeaderHyperlinkClick

The **OnRowHeaderHyperlinkClick** event is triggered when any of the row header cell is clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableRowHeaderHyperlink="true" OnRowHeaderHyperlinkClick="PivotClient1_RowHeaderHyperlinkClick"></ej:PivotClient>

{% endhighlight %}

{ {% highlight c# %}

protected void PivotClient1_RowHeaderHyperlinkClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of pivotgrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnColumnHeaderHyperlinkClick

The **OnColumnHeaderHyperlinkClick** event is triggered when any of the column header cell is clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>
{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableColumnHeaderHyperlink="true" OnColumnHeaderHyperlinkClick="PivotClient1_ColumnHeaderHyperlinkClick"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_ColumnHeaderHyperlinkClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnSummaryCellHyperlinkClick

The **OnSummaryCellHyperlinkClick** event is triggered when any of the summary cell is clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.


<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableSummaryCellHyperlink="true" OnSummaryCellHyperlinkClick="PivotClient1_SummaryCellHyperlinkClick"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_SummaryCellHyperlinkClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellContext

The **OnCellContext** event is triggered when any of the cell is right-clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableCellContext="true" OnCellContext="PivotClient1_CellContext"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_CellContext(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellSelection

The **OnCellSelection** event is triggered when any of the cell selected/clicked in PivotGrid. The details of the selected/clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of selected/clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableCellSelection="true" OnCellSelection="PivotClient1_CellSelection"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_CellSelection(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellEdit

The **OnCellEdit** event is triggered when any of the value cell is edited in PivotGrid. The details of the edited cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of edited cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableCellEditing="true" OnCellEdit="PivotClient1_CellEdit"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_CellEdit(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellDoubleClick

The **OnCellDoubleClick** event is triggered when any of the cell is double clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of clicked cell information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableCellDoubleClick="true" OnCellDoubleClick="PivotClient1_CellDoubleClick"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_CellDoubleClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnDrillThrough

The **OnDrillThrough** event is triggered when any of the value cell is clicked in PivotGrid. The details of the drillthrough data information of clicked cell can be obtained at server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of drillthrough data information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" EnableDrillThrough="true" OnDrillThrough="PivotClient1_DrillThrough"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_DrillThrough(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
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

<ej:PivotClient ID="PivotClient1" runat="server" OnPointRegionClick="PivotClient1_PointRegionClick"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_PointRegionClick(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotChart.
}
    
{% endhighlight %}

{% endtabs %}

## OnServerExporting

The **OnServerExporting** event is triggered when a request is made to export the PivotGrid and PivotChart to Excel, PDF and Word document. The PivotClient model details can be obtained from server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotClient information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" ClientIDMode="Static" OnServerExcelExporting="PivotClient1_ServerExporting"></ej:PivotClient>

{% endhighlight %}

 {% highlight c# %}

protected void PivotClient1_ServerExporting(object sender, PivotClientEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotClient.
}
    
{% endhighlight %}

{% endtabs %}
