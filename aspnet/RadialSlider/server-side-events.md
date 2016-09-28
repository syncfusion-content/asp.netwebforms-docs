---
layout: post
title: Server side events | RadialSlider | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: RadialSlider
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
OnChange</td><td>
Event is triggered, when the rating value changes.</td><td>
(Object Sender, RadialSliderEventArgs e)<br/>
e.Value - value of the RadialSlider control<br/>
e.PrevValue - previous value of the RadialSlider control</td></tr>
</table>

The following step explains you how to define server side event for RadialSlider control.

In an ASPX page, define the RadialSlider control. 

{% tabs %}

{% highlight html %}

    <ej:RadialSlider ID="slider" OnChange="slider_Change" runat="server"></ej:RadialSlider>

{% endhighlight %}

{% highlight c# %}

    protected void slider_Change(object sender, Syncfusion.JavaScript.Web.RadialSliderEventArgs e)
    {
    //e.Value - value of the RadialSlider
    // e.PrevValue - previous value of the RadialSlider
    }
    
{% endhighlight %}

{% endtabs %}
