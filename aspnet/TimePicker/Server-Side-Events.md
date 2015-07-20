---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: TimePicker
documentation: ug
---

# Server Side Events

The following are the server side events available in the TimePicker control.

<table>
<tr>
<td>
Event</td><td>
Event Description</td><td>
Event Description</td></tr>
<tr>
<td>
OnSelect</td><td>
Occurs when selecting the time value in{{ '![fdgfdhtd](Cell-or-Range-Formatting_images/Cell-or-Range-Formatting_img1.png)' | markdownify }}</td><td>
Event Argument contains parameters aree.EventType – Event Name.e.{{ '_Value_' | markdownify }} – It holds current selected time value.e.Arguments – Contain keys and values for event args.</td></tr>
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



