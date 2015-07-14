---
layout: post
title: Localization-Support
description: localization support
platform: aspnet
control: PercentageTextBox
documentation: ug
---

## Localization Support

Localization is language support based on the culture in PercentageTextbox. You can achieve the Localization by using “Locale” property in PercentageTextbox.

The PercentageTextbox control provides multi-language support by using globalization. You can customize the PercentageTextbox with your own language style by using this feature. You can change the localization by using the Locale property. The default value for Locale property is en-US in PercentageTextbox control.

In order to enable [localization](http://help.syncfusion.com/ug/js/default.htm) refer to the following scripts: globalize.cultures.js and globalize.js. The “globalize.cultures.js” includes different language support for JavaScript controls and the “globalize.js” is a simple JavaScript library that allows you to format the value based on the specified culture.

You can refer to the following online link reference for globalize.js

[http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js](http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js)

You can refer to the following online link reference for globalize.culture.js

[http://ajax.aspnetcdn.com/ajax/globalize/0.1.1/cultures/globalize.cultures.js](http://ajax.aspnetcdn.com/ajax/globalize/0.1.1/cultures/globalize.cultures.js)

You can get the script file of various cultures from the following path also:

"&lt;Installed Location&gt;\Syncfusion\Essential Studio\ {{site.releaseversion}} \JavaScript\assets\external\cultures"

You can dynamically change the language based on their culture.

### Configuring Localization

Add the following code example in your ASPX page to render PercentageTextbox control.

{% highlight html %}

<ej:PercentageTextBox ID="percentage" Value="21234" DecimalPlaces="3" Locale="es-ES" runat="server"> </ej:PercentageTextBox>



{% endhighlight %}



{ ![](Localization-Support_images/Localization-Support_img1.png) | markdownify }
{:.image }
The output for PercentageTextbox with localization.

_PercentageTextbox with es-ES locale_

_PercentageTextbox with en-US locale_

{ ![](Localization-Support_images/Localization-Support_img2.png) | markdownify }
{:.image }
__

