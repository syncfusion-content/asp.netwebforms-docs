---
layout: post
title: Localization | PivotGauge | ASP.NET | Syncfusion
description: This document illustrates that how to define localization with respective to the modes in ASP.NET PivotGauge control
platform: aspnet
control: PivotGauge
documentation: ug
---

# Localization

## Localization in pivot gauge control
 You can localize the pivot gauge control texts with a collection of localized strings by using the **"ej.PivotGauge.Locale"** for different cultures.
 
 N> By default, the pivot gauge control is localized in **"en-US"**.
 
Following code example illustrates how to localize the pivot gauge based on the **"French"** culture:

{% highlight html %}

    <script>
        ej.PivotGauge.Locale["fr-FR"] = {
            RevenueGoal: "Objectif de chiffre d'affaires",
            RevenueValue: "Valeur du chiffre d'affaires"
        }
    </script>

    <ej:PivotGauge ID="PivotGauge1" runat="server" Locale="fr-FR">

    </ej:PivotGauge>

{% endhighlight %}

Following table localizes the in-built keywords to **"French"** culture for the pivot gauge:

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

## Localization and globalization of cube info

The content displayed within the pivot gauge control is obtained from the OLAP cube. The following are the steps that should be done to get the localized and globalized cube content.

To get the localized string based on different cultures, set the **"Locale Identifier"** in the connection string to a specific culture in the OLAP cube. The attribute is set for the pivot gauge in client mode as shown below:

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server" Locale="fr-FR">
         <DataSource Data="http://bi.syncfusion.com/olap/msmdpump.dll;Locale Identifier=1036;"></DataSource>
    </ej:PivotGauge>

{% endhighlight %}

For server mode, set the **"Culture"** and **"OverrideDefaultFormatStrings"** properties in the OlapDataManager class to a specific culture along with the setting **"Locale Identifier"** in the connection string.

{% highlight C# %}

    //1036 refers to “fr-FR” culture.
    string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
    DataManager = new OlapDataManager(connectionString);
    DataManager.Culture = new System.Globalization.CultureInfo(1036);
    DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![ASPNET PivotGauge Localization-and-Translation-Support Image](Localization-and-Translation-Support_images/Localization.png) 
