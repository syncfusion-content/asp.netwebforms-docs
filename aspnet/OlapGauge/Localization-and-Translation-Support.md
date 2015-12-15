---
layout: post
title: Localization | OLAPGauge | ASP.NET | Syncfusion
description: localization
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Localization

## Localization in OlapGauge Control
We can localize the OlapGauge controls text with a collection of localized strings using **"ej.olap.OlapGauge.locale"** for different cultures. By default, the OlapGauge control is localized in **"en-US"**.

Following code example illustrates on how to localize OlapGauge based on **"French"** culture.

{% highlight html %}

<script>
    ej.olap.OlapGauge.locale["fr-FR"] = {
        RevenueGoal: "Objectif de chiffre d'affaires",
        RevenueValue: "Valeur du chiffre d'affaires"
    }
</script>

<ej:OlapGauge ID="OlapGauge1" Url="../OlapGauge" runat="server" Locale="fr-FR">
</ej:OlapGauge>

{% endhighlight %}

Following table localizes the in-built keywords to **"French"** culture for OlapGauge.

<table>
<tr>
<th>
Keywords</th><th>
Values</th></tr>
<tr>
<td>
RevenueGoal</td><td>
"Objectif de chiffre d'affaires"</td></tr>
<tr>
<td>
RevenueValue</td><td>
"Valeur du chiffre d'affaires "</td></tr>
</table>

## Localization and Globalization of Cube Info

Content displayed within the OlapGauge control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.
 
* To get the localized string based on different cultures, from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture. 
* To bind the globalized content in OlapGauge control, we need to set **"Culture"** and **"OverrideDefaultFormatStrings"** properties in OlapDataManager class to a specific culture. 

{% highlight C# %}

//1036 refers to “fr-FR” culture.
string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
DataManager = new OlapDataManager(connectionString);
DataManager.Culture = new System.Globalization.CultureInfo(1036);
DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![](Localization_images/Localization.png) 
