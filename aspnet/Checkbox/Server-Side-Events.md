---
layout: post
title: Server Side Events | Checkbox | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Checkbox
documentation: ug
---

# Server Side Events

The following are the server side events available in the CheckBox control.

<table>
<tr>
<td>
{{ '**Event**' | markdownify }}</td><td>
{{ '**Event Description**' | markdownify }}</td><td>
{{ '**Argument Details**' | markdownify }}</td></tr>
<tr>
<td>
OnChange</td><td>
It raises when the Checkbox status is changed from checked to uncheck / unchecked to check.</td><td>
Event Argument contains the following parameters,e.IsChecked – Status of Checkbox.e.EventType – Event Name.Arguments – Contain keys and values for IsChecked.</td></tr>
</table>


In the ASPX page, add the CheckBox control to configure Checkbox events.

{% highlight html %}

<%--Adds serverside event for CheckBox control as follows--%>



<ej:CheckBox ID="Checkbox" runat="server" Text="Milk" OnChange="CheckBox_Change">

</ej:CheckBox>





{% endhighlight %}

Define Checkbox_Change server side event in the code behind.

{% highlight c# %}

protected void Checkbox_Change(object sender, Syncfusion.JavaScript.Web.CheckBoxEventArgs e)

{



//e.IsChecked – Status of Checkbox

//e.EventType – Event Name

//e.Arguments – Contain keys and values for IsChecked

 }



{% endhighlight %}



