---
layout: post
title: Server side events | PivotTreeMap | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: PivotTreeMap
documentation: ug
---

## Server side event arguments in ASP PivotTreeMap

This section explains in detail about the various server-side events available in the control and the arguments that are obtained at server-side. 

The **sender** parameter of all the server-side events returns the PivotTreeMap model details. The **Syncfusion.JavaScript.Web.PivotTreeMapEventArgs** arguments provide information specific to this event.

The various server-side events and the arguments corresponding to the events are as follows:

## OnDrillSuccess

The **OnDrillSuccess** event is triggered while performing drill operation on TreeMap. The details of the drilled tile information can be obtained at server-side, as explained in the following table.

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

<ej:PivotTreeMap ID="PivotTreeMap1" runat="server" OnDrillSuccess="PivotTreeMap1_DrillSuccess"></ej:PivotTreeMap>

{% endhighlight %}

 {% highlight c# %}

protected void PivotTreeMap1_DrillSuccess(object sender, PivotTreeMapEventArgs e)

{
    //e.EventType – Event Name
    //e.Argument – Contain keys and values of PivotTreeMap.
}
    
{% endhighlight %}
    
{% endtabs %}