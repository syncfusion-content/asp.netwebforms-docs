---
layout: post
title: Server Side Events | Toggle Button | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: ToggleButton
documentation: ug
---

# Server Side Events

The following given server side even is available in the ToggleButton control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Argument Details</th></tr>
<tr>
<td>
OnChange</td><td>
It is raised when the Toggle Button is clicked.</td><td>
<br/>
Event Argument contains the following parameters:<br/><br/>
e.Status - Status of ToggleButton.<br/><br/>
e.IsChecked - Checked Status of ToggleButton<br/><br/>
e.EventType - Event Name<br/><br/>
e.Arguments - Contain keys and values for Status.<br/>
</td></tr>
</table>


 In the ASPX page, add the Button control to configure the ToggleButton events.

{% highlight html %}

<ej:ToggleButton ID="ToggleButton_Prevent" runat="server" Size="Small" DefaultText="Play" ActiveText="Pause" OnChange="ToggleButton_Prevent_Change">

</ej:ToggleButton>

{% endhighlight %}

The code Define ToggleButton Prevent Change server side event in behind.

{% highlight c# %}

protected void ToggleButton_Prevent_Change(object Sender, Syncfusion.JavaScript.Web.ToggleButtonEventArgs e)

{

	//e.Status – Status of the ToggleButton

	//e.EventType – Event Name

	//e.IsChecked – Checked Status of the Togglebutton

	//e.Argument – Contain keys and values for Status
}
	
{% endhighlight %}