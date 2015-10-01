---
layout: post
title: Server Side Events | ListBox | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: ListBox
documentation: ug
---

## Server Side Events

The following server side event is available in Listbox control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Event Description</th></tr>
<tr>
<td>
OnCheckChange</td><td>
Occurs when CheckBox value is changed.</td><td>
Event Argument contains the following parameters.<br/><br/>
e.IsChecked – Status of Listbox Checkbox.<br/><br/>
e.Text – Text of Listbox Selected item.<br/><br/>
e.Value – Value of Listbox Selected item.<br/><br/>
e.SelectedText –Text of Listbox Selected item.<br/><br/>
e.ItemId – Index Value of Listbox Selected item.<br/><br/>
e.EventType – Event Name<br/><br/>
e.Arguments – Contain keys and values for SelectedText and Args.<br/> 
</td></tr>
<tr>
<td>
OnValueSelect</td><td>
Occurs when Listbox Active Node is changed</td><td>
Event Argument contains the following parameters.<br/><br/>
e.IsChecked – Status of Listbox Checkbox.<br/><br/>
e.Text – Text of Listbox Selected item.<br/><br/>
e.Value – Value of Listbox Selected item.<br/><br/>
e.SelectedText –Text of Listbox Selected item.<br/><br/>
e.ItemId – Index Value of Listbox Selected item.<br/><br/>
e.EventType – Event Name<br/><br/>
e.Arguments – Contain keys and values for SelectedText and Args.<br/>
</td></tr>
<tr>
<td>
OnIndexChanged</td><td>
Occurs when selected list item Index is Change.</td><td>
Event Argument contains the following parameters.<br/><br/>
e.IsChecked – Status of Listbox Checkbox.<br/><br/>
e.Text – Text of Listbox Selected item.<br/><br/>
e.Value – Value of Listbox Selected item.<br/><br/>
e.SelectedText –Text of Listbox Selected item.<br/><br/>
e.ItemId – Index Value of Listbox Selected item.<br/><br/>
e.EventType – Event Name<br/><br/>
e.Arguments – Contain keys and values for SelectedText and Args.<br/>
</td></tr>
</table>

In an ASPX page, add the Listbox control to configure Listbox events.

{% highlight html %}

<%--Add serverside event for ListBox control as follows--%>

<ej:ListBox ID="listboxsample" DataTextField="CustomerID" OnValueSelect="listboxsample_CheckChange" runat="server">

</ej:ListBox>

{% endhighlight %}



The following code example define listboxsample _ValueSelect server side event in behind.

{% highlight c# %}

    // Add the code in cs page



    protected void Page_Load(object sender, EventArgs e)

    {

        this.listboxsample.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";

        this.listboxsample.Query = "ej.Query().from('Customers')";

    }

    protected void listboxsample_CheckChange(object sender, Syncfusion.JavaScript.Web.ListBoxEventArgs e)

    {

        //e.IsChecked – Status of Checkbox

        //e.EventType – Event Name

        //e.Arguments – Contain keys and values for SelectedText and Args

        //e.Text – Text value of selected node

        //e.Value – Value of selected node

        //e.SelectedText – Text  of selected node

        //e.ItemId – Index value of slected node

    }

{% endhighlight %}