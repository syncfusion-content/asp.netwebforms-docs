---
layout: post
title: Server Side Events | CurrencyTextBox | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Currency TextBox
documentation: ug
---

# Server Side Events

The server side event present in the CurrencyTextbox control is listed:


<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers when the focus has been moved out from the TextBox.</td><td><br/><br/>
e.Value - Value of the CurrencyTextbox.<br/><br/>
e.EventType - Event Name.<br/><br/>
e.Arguments - Contain keys and value of the CurrencyTextbox.<br/><br/></td></tr>
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

    Response.Write("Server side event has been triggered");

}



{% endhighlight %}



