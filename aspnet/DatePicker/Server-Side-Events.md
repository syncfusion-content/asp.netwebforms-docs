---
layout: post
title: Server Side Events | DatePicker | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: DatePicker
documentation: ug
---

# Server Side Events

The following are the server side events available in the DatePicker control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnValueSelect</td><td>
Occurs when selecting the Date in the DatePicker.</td><td>
Event Argument contains the following parameters, 
<ul>
<li>e.EventType – Event Name.</li>
<li>e.isSpecialDay – Returns the boolean value for the selected date whether special day or not.</li>
<li>e.PreviousDate – Holds the previously selected value.</li>
<li>e.Value – Holds current selected date value.</li>
<li>e.Arguments – Contains keys and values for event args.</li>
</ul></td></tr>
</table>




In the ASPX page, add the DatePicker control to configure the DatePicker events.

{% tabs %}

{% highlight html %}



<ej:DatePicker ID="datepicker" runat="server" OnSelect=" datepicker_Select"> </ej:DatePicker>

{% endhighlight %}

{% highlight c# %}

protected void datepicker_Select(object sender, Syncfusion.JavaScript.Web. DatePickerSelectEventArgs e)

    {

//e.EventType – Event Name

//e.Arguments – Contains keys and values for Event and Args

//e. PreviousDate – It holds the previously selected date value.

//e.Value – selected date value.

//e.isSpecialDay– Returns the boolean value for the selected date whether special day or not



    }



{% endhighlight %}

{% endtabs %}

