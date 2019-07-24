---
layout: post
title: Orientation | Slider | ASP.NET | Syncfusion
description: orientation
platform: aspnet
control: Slider
documentation: ug
---

# Orientation

This property is used to set the Slider either in horizontal or vertical direction. By default, Slider renders in horizontal direction. Data type of this property is enum.

Possible Slider orientations are as follows,

<table>
<tr>
<th>
Property</th><th>
Allowed values</th><th>
Description</th></tr>
<tr>
<td rowspan = "2">
Orientation</td><td>
Vertical</td><td>
Displays the Slider in a vertical direction.</td></tr>
<tr>
<td>
Horizontal (default value)</td><td>
Displays the Slider in a horizontal direction.</td></tr>
</table>


In an ASPX page, define the Slider control and configure the Orientation property as required.

{% highlight html %}

<ej:Slider ID="VerticalSlider" runat="server" Height="150" Width="20" Orientation="Vertical"></ej:Slider>

{% endhighlight %}



The following screenshot displays the output of the above code example.

 ![Slider Orientation](Orientation_images/Orientation_img1.png)



