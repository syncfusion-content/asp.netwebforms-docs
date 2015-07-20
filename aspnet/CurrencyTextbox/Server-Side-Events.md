---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: Currency TextBox
documentation: ug
---

# Server Side Events

The server side event present in the CurrencyTextbox control is listed:


<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers when the focus has been moved out from the TextBox.</td><td>
e.Value - Value of the CurrencyTextbox.e.EventType - Event Name.e.Arguments - Contain keys and value of the CurrencyTextbox.</td></tr>
</table>


The following steps explain how to define the server side event for the CurrencyTextbox control.

In an ASPX page, add the CurrencyTextbox control with OnFocusOut server side event as shown in the following code example.

{% highlight html %}

  <ej:CurrencyTextBox ID="currency" Value="11" OnFocusOut="focus"  runat="server" ></ej:CurrencyTextBox>



{% endhighlight %}

In the code behind, define the action to be performed.

{% highlight c# %}

protected void focus(object Sender, EventArgs e)

{

     Response.Write("Serverside event has been trigerred");

}



{% endhighlight %}



