---
layout: post
title: Server Side Events for DropDownList in Syncfusion ASP.NET Webforms
description: Server Side Events for DropDownList in Syncfusion ASP.NET Webforms
platform: aspnet
control: DropDownList
documentation: ug
keywords: Server Side Events, DropDownList, dropdown, server side, events
---

# Server Side Events

The following are the server side events available in the DropDownList control.

<table>
<tr><th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnCheckChange</td><td>
Occurs when CheckBox value is change.</td><td>
Event Argument contains the following parameters,
<ul>
<li>e.IsChecked – Status of the DropDownList Checkbox.</li>
<li>e.Text – Text of the DropDownList Selected list.</li>
<li>e.Value – Value of the DropDownList Selected list.</li>
<li>e.SelectedText – Selected Node Text of the DropDownList Selected list.</li>
<li>e.ItemId – Index Value of the DropDownList Selected list.</li>
<li>e.EventType – Event Name.</li>
<li>e.Arguments – Contain keys and values for IsChecked, Text, Value, SelectedText and ItemId.</li>
</ul>
</td></tr>
<tr>
<td>
OnValueSelect</td><td>
Occurs when DropDownList Active list changes.</td><td>
Event Argument contains the following parameters, 
<ul>
<li>e.IsChecked – Status of DropDownList Checkbox.</li>
<li>e.Text – Text of the DropDownList Selected list.</li>
<li>e.Value – Value of the DropDownList Selected list.</li>
<li>e.SelectedText – Selected Node Text of the DropDownList Selected list.</li>
<li>e.ItemId – Index Value of the DropDownList Selected list.</li>
<li>e.EventType – Event Name.Arguments – Contain keys and values for IsChecked, Text, Value, SelectedText and ItemId.</li>
</ul></td></tr>
</table>

In the ASPX page, add the DropDownList control to configure the DropDownList events.

{% highlight html %}

    <ej:DropDownList ID="dropdownlist" TargetID="list" Width="200px" OnValueSelect="dropdownlist_ValueSelect" ShowCheckbox="true" OnCheckedChange="dropdownlist_CheckedChange" runat="server" OnCascade="dropdownlist_Cascade" OnSearch="dropdownlist_Search" >

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

The code Define dropdownlist ValueSelect server side event in behind.

{% highlight c# %}

    protected void dropdownlist_ValueSelect(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)

    {


        //e.EventType – Event Name

        //e.Arguments – Contain keys and values for IsChecked,Text,Value,SelectedText and ItemId

        //e.Text – Text value of selected node

        //e.Value – Value of selected node

        //e.SelectedText – Text  of selected node

        //e.ItemId – Index value of selected node

    }
	
	protected void dropdownlist_CheckedChange(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)
	{
	    //e.IsChecked – Status of Checkbox
	}

	protected void dropdownlist_Cascade(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)
	{
        //e.CascadeValue - Get the cascaded DropDownList value
	}

	protected void dropdownlist_Search(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)
	{
        // e.SearchString - Entered search string in textbox
        // e.SearchedListItems - Get the list of items searched
	}


{% endhighlight %}