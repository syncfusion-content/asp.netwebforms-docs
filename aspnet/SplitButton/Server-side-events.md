---
layout: post
title: Server side events | SplitButton | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: SplitButton
documentation: ug
---

# Server-side events

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Parameters</th></tr>
<tr>
<td>
OnClickEvent</td><td>
Event triggered when the Split Button is clicked</td><td>
(Object Sender, SplitButtonEventArgs e)
<br/>
e.Status - Status of the Split Button whether it’s true or false.</td></tr>
<tr>
<td>
OnItemSelect</td><td>
Event triggered when select the item in the split button</td><td>
(Object Sender,SplitButtonSelectEventArgs e)
<br/>
 e.MenuId –id of the selected item <br/>
 e.MenuText –Text of the selected item</td></tr>
</table>


The following step explains on how to define server side event for Split Button control.

In an ASPX page, define the Split Button control.

{% highlight html %}

<ej:SplitButton ID="SplitButton" runat="server" Size="Large" ShowRoundedCorner="true" Text="Save" OnClick="SplitButton_Click" OnItemSelect="SplitButton_ItemSelect">

       <Items>

          <ej:SplitItem Text="Open"></ej:SplitItem>

          <ej:SplitItem Text="Save"></ej:SplitItem>

          <ej:SplitItem Text="Delete"></ej:SplitItem>

       </Items>

</ej:SplitButton>

{% endhighlight %}



In CS page, define the events for Click and ItemSelect Event.

{% highlight c# %}

protected void SplitButton_Click(object Sender, Syncfusion.JavaScript.Web.SplitButtonEventArgs e)
{

	   // e.Status - returns the status of the Split Button   

}

protected void SplitButton_ItemSelect(object Sender, Syncfusion.JavaScript.Web.SplitButtonSelectEventArgs e)
{

	 // e.MenuId- returns the current ID of Split Button

	 // e.MenuText- returns the current text of Split Button

}


{% endhighlight %}
