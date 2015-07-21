---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: ProgressBar
documentation: ug
---

# Server Side Events

The server side event present in the Dialog control is as follows.

<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
OnComplete</td><td>
Triggered when the value defined in progress bar sets completely.</td><td>
e.Value - Value of the Progressbar.e.EventType -  Event Namee.Arguments  - Contain keys and value of Progressbar.</td></tr>
</table>
In an ASPX page, add the ProgressBar control with OnComplete server side event as shown in the following code example.

{% highlight html %}



<ej:ProgressBar ID="progressbar" runat="server" OnComplete="onComplete" Value="70" Text="70 %"  Height="20" Width="500"></ej:ProgressBar>



{% endhighlight %}

In the code behind define the action to be performed.

{% highlight c# %}



protected void onComplete(object Sender, EventArgs e)

{

     Response.Write("Serverside event has been trigerred");

}



{% endhighlight %}



