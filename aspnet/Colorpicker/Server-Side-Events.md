---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: ColorPicker
documentation: ug
---

# Server Side Events

The server side events present in the ColorPicker control are as follows.


<table>
<tr>
<th>
{{ '**Event Name**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Arguments**' | markdownify }}</th></tr>
<tr>
<td>
OnSelect</td><td>
triggers on selecting any color</td><td>
e.Value– Value of the Colorpickere.EventType – Event Namee.Arguments – Contain keys and value of Colorpicker</td></tr>
</table>



In an ASPX page, add the ColorPicker control with the OnSelect server side event as shown in the following code example.



{% highlight html %}

<ej:ColorPicker runat="server" ID="colorpicker" OnSelect="onSelect" Value="#278787"> </ej:ColorPicker>



{% endhighlight %}



In the code behind define the action to be performed.



{% highlight c# %}

protected void onSelect(object Sender, EventArgs e)

{

     Response.Write("Serverside event has been triggered");

}



{% endhighlight %}



