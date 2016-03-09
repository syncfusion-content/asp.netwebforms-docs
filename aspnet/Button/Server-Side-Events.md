---
layout: post
title: Server Side Events | Button | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Button
documentation: ug
---

# Server Side Events

The following server side event is available in Button control.

<table>
<tr>
<td>
{{ '**Event**' | markdownify }}</td><td>
{{ '**Event Description**' | markdownify }}</td><td>
{{ '**Argument Details**' | markdownify }}</td></tr>
<tr>
<td>
OnClick</td><td>
Triggers when the button is clicked. </td><td>
Event Argument contains parameters are .Status – Status of Button.e.EventType – Event Name.Arguments – Contain keys and values for Status.</td></tr>
</table>
In the ASPX page, add the Button control to configure Button events.

{% highlight html %}

<%--Add serverside event for button control as follows--%>

<ej:Button ID="Button" runat="server" Type="Button" Text="button" Size="Mini" OnClick="Button_Click">

</ej:Button>



{% endhighlight %}

The code Define Button_Click server side event in behind.

{% highlight c# %}

protected void Button_Click(object sender, Syncfusion.JavaScript.Web.ButtonEventArgs e) {

//e.Status – Status of Button

//e.EventType – Event Name

//e.Argument – Contain keys and values for Status

}



{% endhighlight %}







