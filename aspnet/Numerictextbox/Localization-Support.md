---
layout: post
title: Localization-Support
description: localization support
platform: aspnet
control: NumericTextbox
documentation: ug
---

# Localization Support

Localization is a language support based on the culture in the NumericTextbox. You can achieve Localization by using the “Locale” property in the NumericTextbox.

The NumericTextbox control provides multi-language support by using the globalization. You can customize the NumericTextbox with your own language style by using this feature. You can change the localization by using the Locale property. The default value for Locale property is en-US in the NumericTextbox control.

In order to enable [localization](http://help.syncfusion.com/ug/js/default.htm), refer to the following scripts: globalize.cultures.js and globalize.js. The “globalize.cultures.js” includes different language support for JavaScript controls and the “globalize.js” is a simple JavaScript library that allows you to format the value based on the specified culture.

You can refer to the following online link reference for globalize.js

[http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js](http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js)

You can refer to the following online link reference for globalize.culture.js

[http://ajax.aspnetcdn.com/ajax/globalize/0.1.1/cultures/globalize.cultures.js](http://ajax.aspnetcdn.com/ajax/globalize/0.1.1/cultures/globalize.cultures.js)

You can get the script file of various cultures from the following path:

"&lt;Installed Location&gt;\Syncfusion\Essential Studio\&lt;version&gt;\JavaScript\assets\external\cultures"

You can dynamically change the language based on their culture.

## Configuring Localization

Add the following code example in your ASPX page to render the NumericTextbox control.



{% highlight html %}

<ej:NumericTextBox ID="numeric" Value="12345" DecimalPlaces="2" Locale="es-ES" runat="server"> </ej:NumericTextBox>



{% endhighlight %}



The following screenshot displays the output of the NumericTextbox with localization.

![C:/Users/giftline.jebamani/Desktop/n.png](Localization-Support_images/Localization-Support_img1.png) 
{:.image }
![C:/Users/giftline.jebamani/Desktop/na.png](Localization-Support_images/Localization-Support_img2.png) 
{:.image }


