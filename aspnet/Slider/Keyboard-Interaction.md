---
layout: post
title: Keyboard Interaction | Slider | ASP.NET | Syncfusion
description: keyboard interaction
platform: aspnet
control: Slider
documentation: ug
---

# Keyboard Interaction
 
You can use Keyboard shortcut keys as an alternative to the mouse for using the Slider control. All options in the Slider can be accessed by using keyboard shortcuts. The following table explains the keyboard shortcut keys and the operations that can be performed by using the corresponding keys.

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Alt + j                           </td><td>
Focuses into the Slider handle.</td></tr>
<tr>
<td>
Up/Right</td><td>
Increments the Slider value.</td></tr>
<tr>
<td>
Down/Left</td><td>
Decrements the Slider value.</td></tr>
<tr>
<td>
Home</td><td>
Slider handle moves to the start value.</td></tr>
<tr>
<td>
End</td><td>
Slider handle moves to the end value.</td></tr>
<tr>
<td>
Esc</td><td>
Focuses out from the Slider handle.</td></tr>
</table>

## Configure keyboard interaction

The following steps explain you how to enable keyboard support in the Slider.

In an ASPX page, define the Slider control with Range Slider. 

{% highlight html %}

<ej:Slider ID="rangeSlider" runat="server" Width="500" Values="25,75" SliderType="Range"></ej:Slider>

{% endhighlight %}



In JavaScript, focus the Slider control in document key down function. 

{% highlight js %}

$(document).on("keydown", function (e) {

	if (e.altKey && e.keyCode === 74) { // j- key code.

		$(" #<%=rangeSlider.ClientID%> a")[0].focus();

	}

});

{% endhighlight %}



