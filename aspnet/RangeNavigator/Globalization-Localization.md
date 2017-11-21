---
layout: post
title: Globalization Localization | RangeNavigator | ASP.NET | Syncfusion
description: globalization & localization
platform: aspnet
control: RangeNavigator
documentation: ug
---

# Globalization & Localization

RangeNavigator supports Localization and Globalization to customize the labels based on a culture specific to a country. The culture defines specific information for the number formats, week and month names, date and time formats etc. 

## Localization

The `Locale` property is used to specify the Localization of RangeNavigator. Localization is the process of customizing the user interface based on a culture specific to a particular country or region in order to display regional data.  The culture is represented by a unique string, for example, en-US‖ for U.S. English and fr-FR‖ for French (common), this is achieved by creating a JavaScript file “rangeNavigatorSource.fr-FR.js” and setting the equivalent word as illustrated in the following code sample.

{% highlight js %}
ej.datavisualization.RangeNavigator.locale["fr-FR"] = {

    intervals: {

        //string to display the intervals on RangeNavigator

        quarter: {longQuarters: "Trimestre", shortQuarters: "T"},

        week: { longWeeks: "Semaine", shortWeeks: "S" }

    }

}
{% endhighlight %}

Localization is the key feature that provides solutions globally with the help of localized control. 

{% highlight html %}
<ej:RangeNavigator ID="RangeNavigator1" runat="server" Locale="fr-FR">

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %}

![](Globalization-Localization_images/Globalization-Localization_img1.png)

Localization
{:.caption}

## RTL

Right-to-Left or RTL describes the ability of application to handle and responds you to communicate with a right-to-left language, like Arabic or Japanese. `EnableRTL` property is used to change the rendering format  to "Right to Left", by default it renders from "Left to Right" in RangeNavigator. 

{% highlight html %}
<ej:RangeNavigator ID="RangeNavigator1" runat="server" EnableRTL="true">

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %}

![](Globalization-Localization_images/Globalization-Localization_img2.png)

RTL
{:.caption}