---
layout: post
title: Localization | PivotGauge | ASP.NET | Syncfusion
description: localization
platform: aspnet
control: PivotGauge
documentation: ug
---

# Localization

## Localization in PivotGauge Control
 We can localize the PivotGauge control texts with a collection of localized strings using **"ej.PivotGauge.locale"** for different cultures.
 
 N> By default, the PivotGauge control is localized in **"en-US"**.
 
Following code example illustrates on how to localize PivotGauge based on **"French"** culture.

{% highlight html %}

    <script>
        ej.PivotGauge.locale["fr-FR"] = {
            RevenueGoal: "Objectif de chiffre d'affaires",
            RevenueValue: "Valeur du chiffre d'affaires"
        }
    </script>

    <ej:PivotGauge ID="PivotGauge1" runat="server" Locale="fr-FR">

    </ej:PivotGauge>

{% endhighlight %}

Following table localizes the in-built keywords to **"French"** culture for PivotGauge.

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

Content displayed within the PivotGauge control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.

To get the localized string based on different cultures, from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture. The attribute is set for PivotGauge in Client Mode as shown below

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server" Locale="fr-FR">
         <DataSource Data="http://bi.syncfusion.com/olap/msmdpump.dll;LocaleIdentifier=1036;"></DataSource>
    </ej:PivotGauge>

{% endhighlight %}

For Server Mode, we need to set **"Culture"** and **"OverrideDefaultFormatStrings"** properties in OlapDataManager class to a specific culture along with setting **"Locale Identifier"** in connection string. 

{% highlight C# %}

    //1036 refers to “fr-FR” culture.
    string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
    DataManager = new OlapDataManager(connectionString);
    DataManager.Culture = new System.Globalization.CultureInfo(1036);
    DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![](Localization-and-Translation-Support_images/Localization.png) 
