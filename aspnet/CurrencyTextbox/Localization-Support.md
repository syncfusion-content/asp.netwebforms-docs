---
layout: post
title: Localization Support | CurrencyTextBox | ASP.NET Webforms | Syncfusion
description: localization support
platform: aspnet
control: Currency TextBox
documentation: ug
---

# Globalization Support

**Globalization** is language support based on the culture in CurrencyTextBox. You can achieve the **Globalization** using “**locale”** property in CurrencyTextBox. 

The CurrencyTextBox widget provides multi-language support using globalization. You can customize the CurrencyTextBox with your own language style by using this feature. You can change the globalization by using the **locale** property. The default value for **locale** property is **en-US** in CurrencyTextBox controls. Also you can specify the [currencySymbol](https://help.syncfusion.com/api/js/ejtextboxes#members:currencysymbol) property when the user wants to overwrite the currency symbol commonly instead of the current culture symbol.

More than 350 culture specific files are available to localize the value. To know more about EJ globalize support, please refer the below link      
 [http://help.syncfusion.com/js/localization](http://help.syncfusion.com/js/localization) 
 
 N> All the culture-specific script files are available within the below specified location, once you have installed Essential Studio in your machine, therefore it is not necessary to download these files explicitly.

<table>
<tr>
<td>

    '(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n'
</td>
</tr>
<tr>
<td>

    For example, If you have installed the Essential Studio package within C:\Program Files (x86), then navigate to the below location, 
    C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n

</td></tr>
</table>

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}


You can dynamically change the language based on their culture.

## Configuring Localization

Add the following code to your ASPX page to render the CurrencyTextbox control.

{% highlight html %}

<ej:CurrencyTextBox ID="currency" Value="33" DecimalPlaces="2" Locale="es-ES"  runat="server"> </ej:CurrencyTextBox>



{% endhighlight %}



The screenshots of the CurrencyTextbox with es-ES locale and en-US locale.

![](Localization-Support_images/Localization-Support_img1.png)



![](Localization-Support_images/Localization-Support_img2.png)



