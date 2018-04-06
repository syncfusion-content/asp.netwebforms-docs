---
layout: post
title: How To | NumericTextbox | ASP.NET Webforms | Syncfusion
description: how to
platform: aspnet
control: NumericTextbox
documentation: ug
---

# How To

## Use Normal Textboxes as Syncfusion textboxes

In an application or a web page, you may use normal textboxes along with other Syncfusion components, since there is no separate EJHelpers for textboxes.

So, you may want to make a normal textbox to look like Syncfusion textbox in order to achieve uniform look and appearance in your web page.

This can be achieved by adding **“e-textbox”** class to the HTML helpers.

By adding this class, the textbox will have standard look and appearance as other components for all the themes supported by Syncfusion.

{% highlight html %}

<asp:TextBox runat="server" CssClass="e-textbox">This is a Normal Textbox</asp:TextBox>

{% endhighlight %}

Textbox will be rendered as shown below

![](How-To_images/normaltextbox_customize.png)

Normal textbox as Syncfusion textbox
{:.caption}
