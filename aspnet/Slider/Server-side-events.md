---
layout: post
title: Server side events | Slider | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: Slider
documentation: ug
---

# Server-side events

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Parameters </th></tr>
<tr>
<td>
OnChangeEvent</td><td>
Event triggered when the slider value is changed.</td><td>
(Object Sender, SliderEventArgs e)<br/><br/>
e.HandleNo - slider index<br/><br/>
e.ID -Id of slider control<br/><br/>
e.Value -current value of slider<br/><br/></td></tr>
</table>

In an ASPX page, define the Slider control 

{% highlight html %}

<ej:Slider ID="sliderEvents" runat="server" Height="16px" SliderType="MinRange" 

Value="30" OnChangeEvent="sliderEvents_ChangeEvent"></ej:Slider>

{% endhighlight %}

{% highlight c# %}

protected void sliderEvents_ChangeEvent(object sender, Syncfusion.JavaScript.Web.SliderEventArgs e)

{

	 // e.HandleNo - returns the slider index

	 // e.ID - returns the id of the slider control

	 // e.Value - returns the current value of slider 



}

{% endhighlight %}