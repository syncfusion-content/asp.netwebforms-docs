---
layout: post
title: Server side events | RichTextEditor | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: RichTextEditor
documentation: ug
keywords: RichTextEditor, Server side events

---

# Server side events

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Parameters</th></tr>
<tr>
<td>
OnToolbarItemClick</td><td>

Event triggered when the RTE tool bar item is clicked</td><td>

(Object Sender, RTEEventArgs e)Values passed in argument are as below,<br/><br/>

CommandName – returns the corresponding toolbar item command<br/>

</td></tr>

</table>
The following steps explains you on how to define server side event for a RTE control.

In an ASPX page, define the RTE control and add server side event

{% highlight html %}

<ej:RTE ID="RTESample" Width="650" Height="440" runat="server" OnToolbarItemClick="RTESample_ToolbarItemClick"></ej:RTE>

{% endhighlight %}

In the code behind define the action to be performed on clicking the toolbar item in RTE

{% highlight c# %}

protected void RTESample_ToolbarItemClick(object sender, Syncfusion.JavaScript.Web.RTEEventArgs e)

{    
    // e.CommandName – returns the currently clicked ToolBar item operation command
}

{% endhighlight %}