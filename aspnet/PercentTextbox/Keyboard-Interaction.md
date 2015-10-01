---
layout: post
title: Keyboard Interaction | PercentageTextBox | ASP.NET | Syncfusion
description: keyboard interaction
platform: aspnet
control: PercentageTextBox
documentation: ug
---

# Keyboard Interaction

With the keyboard navigation enabled in the PercentageTextbox control, it is possible to control the actions of the PercentageTextbox with the provided shortcut keys. Almost all the PercentageTextbox actions that are done through mouse can be controlled with shortcut keys.

The various keyboard shortcuts available within the PercentageTextbox control are discussed in the following table. 

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
<a href="http://en.wikipedia.org/wiki/Access_key">Access key</a> + j</td><td>
Focuses the control</td></tr>
<tr>
<td>
Up</td><td>
Increments the value</td></tr>
<tr>
<td>
Down</td><td>
Decrements the value</td></tr>
<tr>
<td>
Tab</td><td>
Focus the next element</td></tr>
</table>

## Configuring Keyboard Navigation

The following steps explain the implementation of keyboard interaction in PercentageTextbox.

Add the following code example in your ASPX page to render PercentageTextbox control.

{% highlight html %}

<ej:PercentageTextBox ID="percentage" Value="22" runat="server"> </ej:PercentageTextBox>

{% endhighlight %}



Add the following code example in your script section.

{% highlight js %}

$(document).on("keydown", function (e) 

{

    if (e.altKey && e.keyCode === 74) 

    { // j- key code.

          $("#<%=percentage.ClientID%>").siblings(".e-input").focus();

    }

});

{% endhighlight %}


![](Keyboard-Interaction_images/Keyboard-Interaction_img1.png)

Run the sample and press [Access key](http://en.wikipedia.org/wiki/Access_key) + j key to focus the PercentageTextbox control. Perform provided functionality by using the keyboard shortcuts.


