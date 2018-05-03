---
layout: post
title: Localization in DropDownList widget for Syncfusion Essential ASP.NET
description: Localization in DropDownList widget for Syncfusion Essential ASP.NET
platform: aspnet
control: DropDownList
documentation: ug
keywords: Localization, DropDownList, dropdown

---
# Localization

The DropDownList provides option to localize its strings, it is used to adapting the DropDownList to a particular local language. By default, the DropDownList will use the US English (en-US) as its language.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the dropdownlist’s strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the DropDownList in German language (“de-DE”).

{% highlight javascript %}

    ej.DropDownList.Locale["de-DE"] = {
        emptyResultText: "Keine Vorschläge" //replace with your text  
    };
    
{% endhighlight %}

Set the locale property of the DropDownList to the new language.


{% highlight html %}

    <ej:DropDownList ID="DropDownList1" DataTextField="FirstName" DataValueField="EmployeeID" EnableFilterSearch="true" Locale="de-DE" runat="server">
    </ej:DropDownList>

{% endhighlight %}

![](Localization_images/Locale.jpg)
