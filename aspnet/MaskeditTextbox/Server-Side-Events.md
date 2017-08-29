---
layout: post
title: Server Side Events | MaskEdit | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: MaskEdit
documentation: ug
---

## Server Side Events

The server side events present in the MaskEditTextbox control are as follows.

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers the event when the focus has been moved out from textbox.</td><td>
<ul>
<li>e.Value– Value of the MaskEditTextbox</li>
<li>e.EventType – Event Name</li>
<li>e.Arguments – Contain keys and value of MaskEditTextbox</li>
</ul></td></tr>
</table>


The following steps explains on how to define server side event for the MaskEditTextbox control.

In an ASPX page, add the MaskEditTextbox control with the OnFocusOut server side event as shown in the following code example.

{% highlight html %}

  <ej:MaskEdit ID="mask" Value="11" OnFocusOut="focus"  runat="server"></ej:MaskEdit>

{% endhighlight %}

In the code behind, define the action to be performed.

{% highlight c# %}

protected void focus(object Sender, EventArgs e)

{

     Response.Write("Server side event has been triggered");

}

{% endhighlight %}