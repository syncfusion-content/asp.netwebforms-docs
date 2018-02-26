---
layout: post
title: Server side events | PivotGrid | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: PivotGrid
documentation: ug
---

## Server side event arguments in ASP PivotGrid

This section explains in detail about the various server-side events available in the control and the arguments that are obtained at server-side. 

The **sender** parameter of all the server-side events returns the PivotGrid model details. The **Syncfusion.JavaScript.Web.PivotGridEventArgs** arguments provide information specific to this event.

The various server-side events and the arguments corresponding to the events are as follows:

## OnDrillSuccess

The **OnDrillSuccess** event is triggered while performing drill operation on row/columns headers. The details of the drilled cell information can be obtained at server-side, as explained in the following table.

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnDrillSuccess="PivotGrid1_DrillSuccess"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_DrillSuccess(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnValueCellHyperlinkClick="PivotGrid1_ValueCellHyperlinkClick">
    <HyperlinkSettings EnableValueCellHyperlink="true" />
</ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ValueCellHyperlinkClick(object sender, PivotGridEventArgs e)

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnRowHeaderHyperlinkClick="PivotGrid1_RowHeaderHyperlinkClick">
    <HyperlinkSettings EnableRowHeaderHyperlink="true" />
</ej:PivotGrid>

{% endhighlight %}

{ {% highlight c# %}

protected void PivotGrid1_RowHeaderHyperlinkClick(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnColumnHeaderHyperlinkClick="PivotGrid1_ColumnHeaderHyperlinkClick">
    <HyperlinkSettings EnableColumnHeaderHyperlink="true" />
</ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ColumnHeaderHyperlinkClick(object sender, PivotGridEventArgs e)

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnSummaryCellHyperlinkClick="PivotGrid1_SummaryCellHyperlinkClick">
    <HyperlinkSettings EnableSummaryCellHyperlink="true" />
</ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_SummaryCellHyperlinkClick(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellContext

The **OnCellContext** event is triggered when any of the cell right clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" EnableCellContext="true" OnCellContext="PivotGrid1_CellContext"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_CellContext(object sender, PivotGridEventArgs e)

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" EnableCellSelection="true" OnCellSelection="PivotGrid1_CellSelection"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_CellSelection(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellEdit

The **OnCellEdit** event is triggered when any of the value cell edited in PivotGrid. The details of the edited cell information can be obtained at server-side, as explained in the following table.

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" EnableCellEditing="true" OnCellEdit="PivotGrid1_CellEdit"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_CellEdit(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnCellDoubleClick

The **OnCellDoubleClick** event is triggered when any of the cell double clicked in PivotGrid. The details of the clicked cell information can be obtained at server-side, as explained in the following table.

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" EnableCellDoubleClick="true" OnCellDoubleClick="PivotGrid1_CellDoubleClick"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_CellDoubleClick(object sender, PivotGridEventArgs e)

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

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" EnableDrillThrough="true" OnDrillThrough="PivotGrid1_DrillThrough"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_DrillThrough(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}

## OnServerExcelExporting

The **OnServerExcelExporting** event is triggered when a request is made to export the PivotGrid to Excel document. The PivotGrid model details can be obtained from server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotGrid information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnServerExcelExporting="PivotGrid1_ServerExcelExporting"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ServerExcelExporting(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
    
## OnServerPDFExporting

The **OnServerPDFExporting** event is triggered when a request is made to export the PivotGrid to PDF document. The PivotGrid model details can be obtained from server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotGrid information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnServerPDFExporting="PivotGrid1_ServerPDFExporting"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ServerPDFExporting(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
   
## OnServerCSVExporting

The **OnServerCSVExporting** event is triggered when a request is made to export the PivotGrid to CSV document. The PivotGrid model details can be obtained from server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotGrid information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnServerCSVExporting="PivotGrid1_ServerWordExporting"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ServerWordExporting(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
   
## OnServerWordExporting

The **OnServerWordExporting** event is triggered when a request is made to export the PivotGrid to Word file. The PivotGrid model details can be obtained from server-side, as explained in the following table.

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
e.Arguments</td><td>
It consists of PivotGrid information.</td></tr>
<tr>
<td>
e.EventType</td><td>
It indicates the triggered event name.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static" OnServerWordExporting="PivotGrid1_ServerCSVExporting"></ej:PivotGrid>

{% endhighlight %}

 {% highlight c# %}

protected void PivotGrid1_ServerCSVExporting(object sender, PivotGridEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotGrid.
}
    
{% endhighlight %}

{% endtabs %}
