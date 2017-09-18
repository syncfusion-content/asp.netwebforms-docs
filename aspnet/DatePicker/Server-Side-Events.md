---
layout: post
title: Validation
description: Validate the date in server side
platform: aspnet
control: DatePicker
documentation: ug
---

## Server side events

EJWEB DatePicker control supports the Server side events too. This allows you to configure the DatePicker functionality in code-behind also. Please refer the below code, to use the server side events of EJWEB DatePicker

{% highlight html %}

    <ej:DatePicker ID="datePicker" OnSelect="datePicker_Select" runat="server">
    </ej:DatePicker>

{% endhighlight %}


{% highlight cs %}

    protected void datePicker_Select(object sender, Syncfusion.JavaScript.Web.DatePickerSelectEventArgs e)
        {
            // write your custom code here
        }

{% endhighlight %}

Please refer the below table to know more about the available server side events and its arguments in EJWEB DatePicker


<table> <tr> <th> Event</th><th> Event Description</th><th> Event Description</th></tr> <tr> <td> OnSelect</td><td> Occurs when selecting the Date in the DatePicker.</td><td> Event Argument contains the following parameters, <ul> <li>e.EventType – Event Name.</li> <li>e.isSpecialDay – Returns the boolean value for the selected date whether special day or not.</li> <li>e.PreviousDate – Holds the previously selected value.</li> <li>e.Value – Holds current selected date value.</li> <li>e.Arguments – Contains keys and values for event args.</li> </ul></td></tr> </table>
