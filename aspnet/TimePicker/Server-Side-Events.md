---
layout: post
title: Server Side Events | TimePicker | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: TimePicker
documentation: ug
---

# Server Side Events

The following are the server side events available in the TimePicker control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnSelect</td><td>
Occurs when selecting the time value in TimePicker </td><td>
Event Argument contains parameters are<br/><br/>
e.EventType – Event Name.e.Value – It holds current selected time value.<br/><br/>
e.Arguments – Contain keys and values for event args.<br/>
</td></tr>
</table>


In the ASPX page, add the TimePicker control to configure the TimePicker events.

{% highlight html %}

<ej:TimePicker ID="time" OnSelect="time_Select" runat="server"></ej:TimePicker>

{% endhighlight %}



{% highlight c# %}

protected void time_Select(object sender, Syncfusion.JavaScript.Web.TimePickerEventArgs e)

{

	//e.EventType – Event Name

	//e.Arguments – Contains keys and values for Event and Args

	//e.Value – selected time value.

}

{% endhighlight %}