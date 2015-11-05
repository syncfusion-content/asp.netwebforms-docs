---
layout: post
title: Server side events | Rating | ASP.NET | Syncfusion
description: server-side events
platform: aspnet
control: Rating
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
(Object Sender, RatingEventArgs e)<br/>
e.Value - value of the Rating control</td></tr>
</table>

The following step explains you how to define server side event for Rating control.

In an ASPX page, define the Rating control. 

{% tabs %}

{% highlight html %}
<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

    <table>

        <tr>

            <td valign="top">Rating:

            </td>

            <td>

                <ej:Rating ID="Rating1" Value="4" Precision="Exact" OnChange="Rating1_Change" runat="server"></ej:Rating>

            </td>

        </tr>

    </table>

</ div >
{% endhighlight %}

{% highlight c# %}
protected void Rating1_Change(object sender, Syncfusion.JavaScript.Web.RatingEventArgs e)

        {         

            //e.Value -returns the value of the Rating 

        }
{% endhighlight %}

{% endtabs %}
