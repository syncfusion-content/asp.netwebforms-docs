---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: MaskEdit
documentation: ug
---

## Server Side Events

The server side events present in the MaskEditTextbox control are as follows.

<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
OnFocusOut</td><td>
Triggers the event when the focus has been moved out from textbox.</td><td>
e.Value– Value of the MaskEditTextboxe.EventType – Event Namee.Arguments – Contain keys and value of MaskEditTextbox</td></tr>
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

     Response.Write("Serverside event has been trigerred");

}



{% endhighlight %}



