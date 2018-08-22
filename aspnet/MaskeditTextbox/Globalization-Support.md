---
layout: post
title: Globalization Support | MaskEdit | ASP.NET Webforms | Syncfusion
description: Globalization support
platform: aspnet
control: MaskEdit TextBox
documentation: ug
---

# Globalization Support in MaskEdit

We have provided the globalization support in **MaskEdit** control. Our **MaskEdit** control mainly rendered based on the **maskFormat** property, so we have provided the globalization support based on the maskFormat literals. We have given this globalization support option on below maskFormat literals in **MaskEdit** control. You can change the globalization by using the [locale](https://help.syncfusion.com/api/js/ejmaskedit#members:locale) property. The default value for **locale** property is 'en-US' in **MaskEdit** control.

<table class="props">
<thead>
<tr>
<th>Formats</th>
<th class="last">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="formats">
$</td>
<td class="description">Currency symbol value will be changed based on the corresponding culture.</td>
</tr>
<tr>
<td class="formats">
.</td>
<td class="description">Decimal Separator value will be changed based on the corresponding culture.</td>
</tr>
<tr>
<td class="formats">
,</td>
<td class="description">Thousand Separator will be changed based on the corresponding culture.</td>
</tr>
</tbody>
</table>

To know more about EJ globalize support, please refer the below link

[https://help.syncfusion.com/aspnet/globalization](https://help.syncfusion.com/aspnet/globalization)

The following example describes the way to use localization for **MaskEdit** widgets.

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}

Add the following code to your ASPX page to render the MaskEdit control.

{% highlight html %}

<label for="mask">Mask Edit</label>

<ej:MaskEdit InputMode="Text" ID="maskedit" Name="mask" MaskFormat="$99,999.99" runat="server" width="100%" Locale="de-DE"></ej:MaskEdit>

{% endhighlight %}

The screenshots of the MaskEdit with de-DE locale and en-US locale.

![](Globalization-Support_images/Globalization-Support_img1.jpg)



![](Globalization-Support_images/Globalization-Support_img2.jpg)



