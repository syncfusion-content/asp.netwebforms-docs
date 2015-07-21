---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: DropDownList
documentation: ug
---

## Server Side Events

The following are the server side events available in the DropDownList control.

<table>
<tr>
<td>
Event</td><td>
Event Description</td><td>
Event Description</td></tr>
<tr>
<td>
OnCheckChange</td><td>
Occurs when CheckBox value is change.</td><td>
Event Argument contains the following parameters,e.IsChecked – Status of the DropDownList Checkbox.e.Text – Text of the DropDownList Selected list.e.Value – Value of the DropDownList Selected list.e.SelectedText – Selected Node Text of the DropDownList Selected list.e.ItemId – Index Value of the DropDownList Selected list.e.EventType – Event Name.e.Arguments – Contain keys and values for IsChecked, Text, Value, SelectedText and ItemId.</td></tr>
<tr>
<td>
OnValueSelect</td><td>
Occurs when DropDownList Active list changes.</td><td>
Event Argument contains the following parameters, e.IsChecked – Status of DropDownList Checkbox.e.Text – Text of the DropDownList Selected list.e.Value – Value of the DropDownList Selected list.e.SelectedText – Selected Node Text of the DropDownList Selected list.e.ItemId – Index Value of the DropDownList Selected list.e.EventType – Event Namee.Arguments – Contain keys and values for IsChecked, Text, Value, SelectedText and ItemId.</td></tr>
</table>
In the ASPX page, add the DropDownList control to configure the DropDownList events.



{% highlight html %}

<ej:DropDownList ID="dropdownlist" TargetID="list" Width="200px" OnValueSelect="dropdownlist_ValueSelect" ShowCheckbox="true" OnCheckedChange="dropdownlist_ValueSelect" runat="server">

</ej:DropDownList>

<div id="list">

    <ul>

        <li>Art</li>

        <li>Architecture</li>

        <li>Biography</li>

        <li>Comics</li>

        <li>Sports</li>

        <li>Science</li>

    </ul>

</div>





{% endhighlight %}

The code Define dropdownlist___ValueSelect server side event in behind.

{% highlight c# %}

    protected void dropdownlist_ValueSelect(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)

    {

        //e.IsChecked – Status of Checkbox

        //e.EventType – Event Name

        //e.Arguments – Contain keys and values for IsChecked,Text,Value,SelectedText and ItemId

        //e.Text – Text value of selected node

        //e.Value – Value of selected node

        //e.SelectedText – Text  of selected node

        //e.ItemId – Index value of slected node

    }





{% endhighlight %}



