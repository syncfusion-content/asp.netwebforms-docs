---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: PercentageTextBox
documentation: ug
---

# Server Side Events

The server side events present in the PercentageTextbox control are listed as follows.

<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers when the focus is moved out from the textbox</td><td>
e.Value– Value of the Numerictextboxe.EventType – Event Namee.Arguments – Contain keys and value of NumericTextbox</td></tr>
</table>


The following steps explains you on how to define server side event for a NumericTextbox control.

In an ASPX page, add the NumericTextbox control with OnFocusOut server side event as illustrated in the following code example.

{% highlight html %}

  <ej:PercentageTextBox ID="numeric" Value="11" OnFocusOut="focus" runat="server"> </ej:PercentageTextBox>



{% endhighlight %}



In the code behind define the action to be performed.

{% highlight c# %}

protected void focus(object Sender, EventArgs e)

        {

            Response.Write("Serverside event has been trigerred");

        }



{% endhighlight %}



