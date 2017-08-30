---
layout: post
title: Server Side Events | NumericTextbox | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: NumericTextbox
documentation: ug
---

# Server Side Events

The server side events present in the NumericTextbox control are as follows.



<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers when the focus is moved from textBox</td><td>
<ul>
<li>e.Value– Value of the NumericTextbox</li>
<li>e.EventType – Event Name</li>
<li>e.Arguments – Contain keys and value of NumericTextbox</li>
</ul>
</td></tr>
</table>


The following steps explain you on how to define server side event for a NumericTextbox control.

In an ASPX page, add the NumericTextbox with OnFocusOut server side event as shown in the following code example.

{% highlight html %}

<ej:NumericTextBox ID="numeric" Value="11" OnFocusOut="focus"  runat="server" > </ej:NumericTextBox>



{% endhighlight %}

In the code behind, define the action to be performed.

{% highlight c# %}

protected void focus(object Sender, EventArgs e)

        {

            Response.Write("Server side event has been triggered");

        }

{% endhighlight %}