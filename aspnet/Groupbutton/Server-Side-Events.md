---
layout: post
title: Server Side Events | GroupButton | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: GroupButton
documentation: ug
---

# Server Side Events

The following server side event is available in GroupButton control.

<table>
<tr>
<td>
{{ '**Event**' | markdownify }}</td><td>
{{ '**Event Description**' | markdownify }}</td><td>
{{ '**Argument Details**' | markdownify }}</td></tr>
<tr>
<td>
OnItemSelect</td><td>
Triggers when the Groupbutton items are clicked. </td><td>
Event Argument contains parameters are .Status – Status of GroupButton.e.EventType – Event Name. Arguments – Contain keys and values for Status of Groupbutton Items.</td></tr>
</table>
In the ASPX page, add the GroupButton control to add GroupButton events.

{% highlight html %}

<%--Add serverside event for Groupbutton control as follows--%>

<ej:GroupButton ID="server_events" runat="server" OnItemSelect="server_events_ItemSelect">
<Items>
<ej:GroupButtonItem Text="Item1"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Item2" ></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Item3"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}

The code Define Button_Click server side event in behind.

{% highlight c# %}

protected void server_events_ItemSelect(object sender, Syncfusion.JavaScript.Web.GroupButtonEventArgs e)

//e.Status – Status of Button

//e.EventType – Event Name

//e.Argument – Contain keys and values for Status, Selected, Index

}

{% endhighlight %}

## How to access the currently selected item 

The server model of currently selected item can be accessed by using event arguments available in postback event.

The event Argument `e.Arguments` in Postback event contains the following key value pairs. 

<table class="params">
<thead>
<tr>
<th>Index</th>
<th>Key value Pairs</th>
</tr>
</thead>
<tbody>
<tr>
<td class="index">[0]</td>
<td class="key">{[id, s1]}</td>
</tr>
<tr>
<td class="index">[1]</td>
<td class="key">{[selected, true]}</td>
</tr>
<tr>
<td class="index">[2]</td>
<td class="key">{[disabled, false]}</td>
</tr>
<tr>
<td class="index">[3]</td>
<td class="key">{[index, 0]}</td>
</tr>
</tbody>
</table>

Using the above index value, the Server model of currently selected item can be accessed as given below. 

{% highlight c# %}

  // Grp_btn --> Groupbutton ID  
  // Grp_btn.Items  --> Refers to individual items  
  // e.Arguments["index"] --> Refers to currently selected item index  
  
  string itemtext = Grp_btn.Items[(int)e.Arguments["index"]].Text;  

{% endhighlight %}
