---
layout: post
title: Globalization and Localization
description: Globalize formatting and Localize strings in DatePicker  
platform: aspnet
control: DatePicker
documentation: ug
---
# Globalization

EJWEB DatePicker has been provided with Built-in localization support, so that it will be able adapt based on culture specific locale defined for it. 

More than 350 culture specific files are available to localize the date. To know more about EJ globalization support, pleaser refer [EJ globalize](http://help.syncfusion.com/js/localization) support    

N> Seven culture-specific script files are available in the below specified location. For all other culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

<table>
<tr>
<td>
(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n<br/><br/>For example, If you have installed the Essential Studio package within C:\Program Files (x86), then navigate to the below location, <br/><br/>C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n</td></tr>
</table>

To translate our control content from default English to any of the culture, say For example - German language, then you need to refer the **ej.culture.de-DE.min.js** file in your application,

The "en-US" locale is currently being used as default culture in DatePicker. You can set any other culture to DatePicker by using [Locale](http://help.syncfusion.com/js/api/ejdatepicker#members:locale) property. Below code example shows German cultured DatePicker.

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight js %}
   
    <script src="https://cdn.syncfusion.com/js/assets/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}


Set German culture to DatePicker at initialization.

{% highlight html %}

    <ej:DatePicker ID="datepick" Locale="de-DE" runat="server"></ej:DatePicker>

{% endhighlight %}

## Watermark and Today Button Text

By default EJWEB DatePicker input has "select date" as watermark text, you can also change this value by using [WatermarkText](http://help.syncfusion.com/js/api/ejdatepicker#members:watermarktext) property. Also there is a today button in DatePicker calendar which allows you to quick select the current date and its value can be changed by using **ButtonText** property.

{% highlight html %}

    <ej:DatePicker ID="datePicker"  ButtonText="current date" WaterMarkText="enter date value"  runat="server"></ej:DatePicker>

{% endhighlight %}


Based on culture specific, only date gets localized but by changing the watermark and button text, you can completely localize the EJWEB DatePicker UI too.

Refer below code example to update those value based some culture say for example English and German.


{% highlight js %}

        <script>

    //create instance for datePicker.
    // only after control creation we can get dateObj otherwise it throws exception.
    var dateObj = $("#datePicker").ejDatePicker('instance');

    //condition to check English culture and change watermark and button text using dateObj.
    if (ej.cultureObject.name == "en-US") {
        dateObj.option({ buttonText: "Today", watermarkText: "select date" })
    }

    //condition to check German culture and change watermark and button text using dateObj.
    if (ej.cultureObject.name == "de-DE") {
        dateObj.option({ buttonText: "heute", watermarkText: "Datum auswählen" })
    } 
</script>


{% endhighlight %}
