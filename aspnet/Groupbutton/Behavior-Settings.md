---
layout: post
title: Button Type | GroupButton | ASP.NET Webforms | Syncfusion
description: Groupbutton type
platform: aspnet
control: GroupButton
documentation: ug
---

# Behavior settings

Groupbutton provides options through which you can customize the default behavior of Groupbutton control.

## Groupbutton Mode

The default behavior of Groupbutton is like Radiobutton, i.e., only one item can be selected at a time.

{% highlight html %}

<ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="RadioButton"  Size="Large">
<Items>
<ej:GroupButtonItem Text="Daily"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Weekly"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Monthly"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}

![](Behavior-Settings_images/Radiobutton.png)
RadioButton mode {:.caption}

To enable selection of one or more Groupbutton items at a time, you can set the Groupbutton mode to Checkbox. With this, you can toggle the each button’s state to perform actions, since all the button will behave like individual buttons.

{% highlight html %}

<ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="CheckBox" Size="Large">
<Items>
<ej:GroupButtonItem Text="Credit Card"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Debit Card"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Netbanking"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>   

{% endhighlight %}

![](Behavior-Settings_images/Checkbox.png)
CheckBox mode {:.caption}
