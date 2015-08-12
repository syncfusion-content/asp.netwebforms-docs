---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: Toggle Button
documentation: ug
---

# Server Side Events

The following given server side even is available in the ToggleButton control.

<table>
<tr>
<td>
Event</td><td>
Event Description</td><td>
Argument Details</td></tr>
<tr>
<td>
OnChange</td><td>
It is raised when the Toggle Button is clicked.</td><td>
Event Argument contains the following parameters:e.Status - Status of Togglebutton.
e.IsChecked - Checked Status of Togglebutton
e.EventType - Event Name
e.Arguments - Contain keys and values for Status.
</td></tr>
</table>


 In the ASPX page, add the Button control to configure the ToggleButton events.

{% highlight html %}

<ej:ToggleButton ID="ToggleButton_Prevent" runat="server" Size="Small" DefaultText="Play" ActiveText="Pause" OnChange="ToggleButton_Prevent_Change">

</ej:ToggleButton>





{% endhighlight %}

The code Define ToggleButton___Prevent_Change server side event in behind.

{% highlight c# %}

    protected void ToggleButton_Prevent_Change(object Sender, Syncfusion.JavaScript.Web.ToggleButtonEventArgs e)

    {

        //e.Status – Status of the ToggleButton

        //e.EventType – Event Name

        //e.IsChecked – Checked Status of the Togglebutton

        //e.Argument – Contain keys and values for Status



    }



{% endhighlight %}







