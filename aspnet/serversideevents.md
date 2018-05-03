---
layout: post
title: Server-side events Syncfusion ASP.NET controls
description: Server-side events of Syncfusion ASP.NET controls
platform: aspnet
control: Introduction
documentation: ug

---

# Server-side events

This section explains in detail about the various server-side events available in the Syncfusion control and the arguments that are obtained in the server-side.

This allows you to configure the controls functionality in code-behind also.

## DatePicker Server-side event

DatePicker control allows you to configure the DatePicker functionality in code-behind also. Refer to the following code to use the server side events of EJWEB DatePicker.

{% highlight html %}

    <ej:DatePicker ID="datePicker" EnablePersistence="true" runat="server"></ej:DatePicker>

{% endhighlight %}

{% highlight html %}

    protected void datePicker_Select(object sender, Syncfusion.JavaScript.Web.DatePickerSelectEventArgs e) 
    { 
        // write your custom code here 
    }

{% endhighlight %}

Refer to the following table to know more about the available server side events and its arguments in EJWEB DatePicker.

<table> <tr> <th> Event</th><th> Event Description</th><th> Event Description</th></tr> <tr> <td> OnSelect</td><td> Occurs when selecting the Date in the DatePicker.</td><td> Event Argument contains the following parameters: <ul> <li>e.EventType: Event Name.</li> <li>e.isSpecialDay: Returns the boolean value for the selected date, whether special day or not.</li> <li>e.PreviousDate: Holds the previously selected value.</li> <li>e.Value: Holds currently selected date value.</li> <li>e.Arguments: Contains keys and values for event args.</li> </ul></td></tr> </table>
