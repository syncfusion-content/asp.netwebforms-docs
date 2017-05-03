---
layout: post
title: Server Side Events | ProgressBar | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: ProgressBar
documentation: ug
---

# Server Side Events

The server side event present in the Dialog control is as follows.

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnComplete</td><td>
Triggered when the value defined in progress bar sets completely.</td><td>
<ul>
<li>e.Value - Value of the Progressbar.</li>
<li>e.EventType -  Event Name</li>
<li>e.Arguments  - Contain keys and value of Progressbar.</li>
</ul>
</td></tr>
</table>
In an ASPX page, add the ProgressBar control with OnComplete server side event as shown in the following code example.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" OnComplete="onComplete" Value="70" Text="70 %"  Height="20" Width="500">

</ej:ProgressBar>
{% endhighlight %}

In the code behind define the action to be performed.

{% highlight c# %}
protected void onComplete(object Sender, EventArgs e)

{

     Response.Write("Server side event has been triggered");
	 
}
{% endhighlight %}