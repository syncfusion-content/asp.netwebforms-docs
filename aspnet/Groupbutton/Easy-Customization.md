---
layout: post
title: Easy Customization | Button | ASP.NET Webforms | Syncfusion
description: easy customization
platform: aspnet
control: Button
documentation: ug
---

# Easy Customization

Group button and each GroupButton items can be easily customized according to your need using the options available in Groupbutton control. 

## Button Size	

You can render the Groupbutton in different sizes by using the predefined size options for rendering a groupbutton with different sizes. Each size option has different height and width. Mainly it avoids the complexity in rendering groupbutton with complex CSS class. 

<table>
<tr>
<td>
{{ '**Normal**' | markdownify }}</td><td>
Creates button with content size.</td></tr>
<tr>
<td>
{{ '**Mini**' | markdownify }}</td><td>
Creates button with Built-in mini size height, width specified.</td></tr>
<tr>
<td>
{{ '**Small**' | markdownify }}</td><td>
Creates button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
{{ '**Medium**' | markdownify }}</td><td>
Creates button with Built-in medium size height, width specified.</td></tr>
<tr>
<td>
{{ '**Large**' | markdownify }}</td><td>
Creates button with Built-in large size height, width specified.</td></tr>
</table>


Apart from the above mentioned predefined size option, you can set your own width and height of GroupButton by using Height and Width property.

In the ASPX page, add the following GroupButton elements to configure the button size

{% highlight html %}

<%--Set the different size options and custom size Groupbutton control as follows--%>

<ej:GroupButton ID="GroupButton1" runat="server" Size="Mini">
<Items>
<ej:GroupButtonItem Text="Save"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Open"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Delete"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}


![](Easy-Customization_images/mini.png)
Mini sized Groupbutton 
{:.caption}

{% highlight html %}

<%--Set the different size options and custom size Groupbutton control as follows--%>

<ej:GroupButton ID="GroupButton1" runat="server" Size="Medium">
<Items>
<ej:GroupButtonItem Text="Save"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Open"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Delete"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}


![](Easy-Customization_images/medium.png)
Medium sized Groupbutton 
{:.caption}

## Orientation

Groupbutton element can be rendered either in vertical or horizontal orientation by means of the Orientation property available in GroupButton.
You can change the orientation of Groupbutton as given in the below code snippet.

{% highlight html %}

<ej:GroupButton ID="GroupButton3" runat="server" Orientation="Vertical">
<Items>
<ej:GroupButtonItem Text="Save"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Open"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Delete"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}
