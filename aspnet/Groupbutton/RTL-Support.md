---
layout: post
title: RTL Support | Button | ASP.NET Webforms | Syncfusion
description: rtl support
platform: aspnet
control: Button
documentation: ug
---

## RTL Support

In some cases, where you want to display the content in Right to Left direction, you can use RTL support by using the **EnableRTL property**. In RTL mode, when you have more than one content (image/text, image/image) in button, then these content are aligned in right to left format. With this property enabled, the Groupbutton items are rendered in reverse order.

In the ASPX page, add the following Groupbutton to configure the Items with Right to left alignment

{% highlight html %}

<%--Enable the alignment format for GroupButton control as follows--%>

<ej:GroupButton runat="server" ID="GroupButton10" Size="Large" EnableRTL="true">
<Items>
<ej:GroupButtonItem Text="Beverages"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Condiments"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Confections"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}

Here the items are rendered in the reverse order.

![](RTL-Support_images/rtl.png)


