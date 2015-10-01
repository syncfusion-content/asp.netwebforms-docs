---
layout: post
title: Slider Types | Slider | ASP.NET | Syncfusion
description: slider types
platform: aspnet
control: Slider
documentation: ug
---

# Slider Types

This feature allows you to specify the type of Slider. There are three different types of Sliders; Default Slider, Min-Range Slider and Range Slider. Default Slider is rendered, by default. You can use the SliderType property to choose the type of Slider. Data type of this property is Enum.

Both Default Slider and Min-Range Slider have same behavior used to select a single value. In Min-Range Slider, a shadow is considered from the start value to current handle position. But Range Slider contains two handles used to select a range of values and a shadow is considered in between the two handles.

Possible Slider types are as follows,

<table>
<tr>
<th>
Property</th><th>
Allowed values</th><th>
Description</th></tr>
<tr>
<td rowspan = "3">
SliderType</td><td>
Default (default value)</td><td>
It is the default Slider type. It helps select a single value.</td></tr>
<tr>
<td>
MinRange</td><td>
Use this Slider to select a single value. It displays shadow from the start value to the current value.</td></tr>
<tr>
<td>
Range</td><td>
Use this Slider to select a range of values. It displays shadow in between the selection range.</td></tr>
</table>


In an ASPX page, define the Slider control and configure the SliderType property to display RangeSlider and MinRangeSlider.

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Width="500" Value="60" SliderType="MinRange"></ej:Slider>

<ej:Slider ID="RangeSlider" runat="server" Width="500" Values="30,60" SliderType="Range"></ej:Slider>

{% endhighlight %}


The following screenshot displays the output of the above code example.

#### MinRange

![](Slider-Types_images/Slider-Types_img1.png)

#### Range

![](Slider-Types_images/Slider-Types_img2.png)