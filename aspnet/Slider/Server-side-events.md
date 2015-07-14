---
layout: post
title: Server-side-events
description: server-side events
platform: aspnet
control: Slider
documentation: ug
---

## Server-side events

<table>
<tr>
<td>
Event Name</td><td>
Description</td><td>
Parameters </td></tr>
<tr>
<td>
OnChangeEvent</td><td>
Event triggered when the slider value is changed.</td><td>
(Object Sender, SliderEventArgs e)e.HandleNo - slider indexe.ID -Id of slider controle.Value -current value of slider</td></tr>
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



