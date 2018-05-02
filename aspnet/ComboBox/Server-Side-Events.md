---
layout: post
title: Server Side Events for ComboBox in Syncfusion ASP.NET Webforms
description: Server Side Events for ComboBox in Syncfusion ASP.NET Webforms
platform: aspnet
control: ComboBox
documentation: ug
keywords: Server Side Events, ComboBox, ComboBox, server side, events
---

# Server Side Events

The following are the server side events available in the ComboBox control.

<table>
<tr><th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnValueSelect</td><td>
Occurs when ComboBox Active list changes.</td><td>
Event Argument contains the following parameters, 
<ul>
<li>e.IsChecked – Status of ComboBox Checkbox.</li>
<li>e.Text – Text of the ComboBox Selected list.</li>
<li>e.Value – Value of the ComboBox Selected list.</li>
<li>e.SelectedText – Selected Node Text of the ComboBox Selected list.</li>
<li>e.ItemId – Index Value of the ComboBox Selected list.</li>
<li>e.EventType – Event Name.Arguments – Contain keys and values for IsChecked, Text, Value, SelectedText and ItemId.</li>
</ul></td></tr>
</table>

In the ASPX page, add the ComboBox control to configure the ComboBox events.

{% highlight html %}

    <ej:ComboBox ID="selectColor" runat="server" Width="100%" DataTextField="text" OnValueSelect="selectColor_ValueSelect" Placeholder="Choose a color"></ej:ComboBox>

{% endhighlight %}

The code Define ComboBox ValueSelect server side event in behind.

{% highlight c# %}

    protected void selectColor_ValueSelect(object sender, Syncfusion.JavaScript.Web.ComboBoxEventArgs e)
    {
        
    }

{% endhighlight %}