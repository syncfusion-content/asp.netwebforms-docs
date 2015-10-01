---
layout: post
title: Server Side Events | TagCloud | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: TagCloud
documentation: ug
---

# Server Side Events

The following list of Individual server side event is available in the TagCloud control.

<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnSelect</td><td>
Occurs when selecting the item in TagCloud</td><td>
Event Argument contains the following parameters:<br/><br/>
e.EventType - Event Name.<br/><br/>
e.Value - It holds current selected Item value.<br/><br/>
e.URL - It holds ULR value of the selected Item.<br/><br/>
e.Arguments - Contains keys and values for event args.<br/></td></tr>
</table>

In the ASPX page, add the TagCloud control to configure the TagCloud events.

{% highlight html %}

<ej:TagCloud ID="tagcloud" runat="server" OnClick="tagcloud_Click"

   DataTextField="CustomerID" Query="ej.Query().from('Orders').take(10)" DataFrequencyField="EmployeeID">

</ej:TagCloud>

{% endhighlight %}

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{
	this.tagcloud.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";

}

protected void tagcloud_Click(object sender, Syncfusion.JavaScript.Web.TagCloudEventArgs e)

{

	//e.EventType – Event Name

	//e.Arguments – Contains keys and values for Event and Args.

	//e.Value – It holds current selected Item value.

	//e. URL – It holds ULR value of selected Item.

}

{% endhighlight %}