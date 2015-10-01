---
layout: post
title: Server Side Events | DateTimePicker | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: DateTimePicker
documentation: ug
---

# Server Side Events

The following server side even_ts_ are available in the__DateTimePicker control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnFocusOut</td><td>
Occurs when DateTimePicker- textbox focus-out.</td><td>
Event Argument contains the following parameters,e.EventType – Event Name.e.Value – It holds selected DateTime value.e.Arguments – Contain keys and values for event args.</td></tr>
</table>


In the ASPX page, add the DateTimePicker control to configure DateTimePicker events.

{% tabs %}

{% highlight html %}



<ej:DateTimePicker ID="DateTime" OnFocusOut="DateTime_FocusOut" Width="280" runat="server"></ej:DateTimePicker>







{% endhighlight %}



{% highlight c# %}



protected void DateTime_FocusOut(object sender, Syncfusion.JavaScript.Web.DateTimePickerFocusOutEventArgs e)

    {

//e.EventType – Event Name

//e.Value – selected DateTime value.

    }



{% endhighlight %}

{% endtabs %}

