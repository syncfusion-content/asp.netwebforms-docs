layout: post
title:Server-side events Syncfusion ASP.NET controls
description: Server-side events of Syncfusion ASP.NET controls
platform: ASP.NET
control: Introduction
documentation: ug
---

# Server-side events

Events raised by ASP.NET server controls work somewhat differently than events in traditional client forms or in client-based Web applications. The difference arises primarily because of the separation of the event itself from where the event is handled.

In client-based applications, events are raised and handled on the client. In Web Forms pages, on the other hand, events associated with server controls are raised on the client but handled on the Web server by the ASP.NET page framework.

For events raised on the client, the Web Forms control event model requires that the event information be captured on the client and an event message transmitted to the server, via an HTTP post. The page framework must interpret the post to determine what event occurred and then call the appropriate method in your code on the server to handle the event.

Syncfusion control supports the Server side events too. This allows you to configure the controls functionality in code-behind also. 

## DatePicker Server-side Event 

DatePicker control allows you to configure the DatePicker functionality in code-behind also. Please refer the below code, to use the server side events of EJWEB DatePicker.

{% highlight html %}

    <ej:DatePicker ID="datepick" EnablePersistence="true" runat="server"></ej:DatePicker>

{% endhighlight %}

{% highlight html %}

    protected void datepick_Select(object sender, Syncfusion.JavaScript.Web.DatePickerSelectEventArgs e) 
    { 
        // write your custom code here 
    }

{% endhighlight %}

Please refer the below table to know more about the available server side events and its arguments in EJWEB DatePicker

<table> <tr> <th> Event</th><th> Event Description</th><th> Event Description</th></tr> <tr> <td> OnSelect</td><td> Occurs when selecting the Date in the DatePicker.</td><td> Event Argument contains the following parameters, <ul> <li>e.EventType – Event Name.</li> <li>e.isSpecialDay – Returns the boolean value for the selected date whether special day or not.</li> <li>e.PreviousDate – Holds the previously selected value.</li> <li>e.Value – Holds current selected date value.</li> <li>e.Arguments – Contains keys and values for event args.</li> </ul></td></tr> </table>
