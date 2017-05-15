---
layout: post
title: Server Side Events | Toolbar | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: Toolbar
documentation: ug
---

# Server Side Events

The server side events present in the Toolbar control are listed as follows.



<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnItemClick</td><td>
Triggered when the toolbar item is clicked</td><td>
e.Status-Status of the Toolbar<br/><br/>
e.EventType – Event Name<br/><br/>
e.Arguments – Contain keys and value of the Toolbar<br/>
</td></tr>
</table>


The following section explains you on how to define server side event for a Toolbar control.

In an ASPX page, add the Toolbar control with OnItemClick event as shown in the following code example.

{% highlight html %}

<%--Refer Local Data section for style and data bound for toolbar items.--%>

<ej:Toolbar ID="toolbar" runat="server" Width="300px" OnItemClick="toolbar_ItemClick" DataIdField="Id" DataTooltipTextField="Tooltip" DataSpriteCssClassField="Css"></ej:Toolbar>

{% endhighlight %}



In the code behind, define the action to be performed.

{% highlight c# %}

protected void toolbar_ItemClick(object sender, EventArgs e)

{

   Response.Write("Server side event has been triggered");

}

{% endhighlight %}