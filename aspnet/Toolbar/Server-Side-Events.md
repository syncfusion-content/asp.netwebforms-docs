---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: Toolbar
documentation: ug
---

## Server Side Events

The server side events present in the Toolbar control are listed as follows.



<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
OnItemClick</td><td>
Triggered when the toolbar item is clicked</td><td>
e.Status-Status of the Toolbare.EventType – Event Namee.Arguments – Contain keys and value of the Toolbar</td></tr>
</table>


The following section explains you on how to define server side event for a Toolbar control.

In an ASPX page, add the Toolbar control with OnItemClick event as shown in the following code example.

{% highlight html %}



<%--Refer Local Data section for style and data bound for toolbar items.--%>

<ej:Toolbar ID="toolbarcontent" runat="server" Width="300px" OnItemClick="toolbarcontent_ItemClick" DataIdField="Id" DataTooltipTextField="Tooltip" DataSpriteCssClassField="Css"></ej:Toolbar>





{% endhighlight %}



In the code behind, define the action to be performed.

{% highlight c# %}



  protected void toolbarcontent_ItemClick(object sender, EventArgs e)

        {

            Response.Write("Serverside event has been triggered");



        }





{% endhighlight %}



