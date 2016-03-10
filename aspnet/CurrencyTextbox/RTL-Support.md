---
layout: post
title: RTL Support | CurrencyTextBox | ASP.NET Webforms | Syncfusion
description: rtl support
platform: aspnet
control: Currency TextBox
documentation: ug
---

# RTL Support

The CurrencyTextbox provides RTL (Right-To-Left) support. The alignment of the CurrencyTextbox can be changed from Left-To-Right into Right-To-Left. It accepts Boolean values. The default value is false.

## Enable RTL 

Add the following code to your ASPX page to render the CurrencyTextbox control with RTL.

{% highlight html %}

<ej:CurrencyTextBox ID="currency" Value="33" EnableRTL="true"  runat="server"> </ej:CurrencyTextBox>



{% endhighlight %}



The output when the EnableRTL is true. 

![](RTL-Support_images/RTL-Support_img1.png)





