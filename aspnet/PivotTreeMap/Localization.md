---
layout: post
title: Localization | PivotTreeMap | ASP.NET | Syncfusion
description: This document illustrates that how to define localization with respective to the modes in ASP.NET PivotTreeMap control 
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# Localization

## Localization and globalization of cube info (client mode)

The content displayed within the pivot tree map control is obtained from the OLAP cube. The following are the steps that should be done to get the localized and globalized cube content:

* To get the localized data from the OLAP cube, set the **"Locale Identifier"** in the connection string to a specific culture of the **"Data"** property present in the **"DataSource"**.

{% highlight js %}

//1036 refers to “fr-FR” culture.
<ej:PivotTreeMap ID="PivotTreeMap1" runat="server" IsResponsive="true" ClientIDMode="Static">
  <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll; Locale Identifier=1036;">
     //...
  </DataSource>
</ej:PivotTreeMap>

{% endhighlight %}

## Localization and globalization of cube info (server mode)

The content displayed within the pivot tree map control is obtained from the OLAP cube. The following are the steps that should be done to get the localized and globalized cube content.

* To get the localized string based on different cultures, set the **"Locale Identifier"** in the connection string to a specific culture in the OLAP cube. 
* To bind the globalized content in the pivot tree map control, set **"Culture"** and **"OverrideDefaultFormatStrings"** properties in the OlapDataManager class to a specific culture.
 
{% highlight c# %}

//1036 refers to “fr-FR” culture.
string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
DataManager = new OlapDataManager(connectionString);
DataManager.Culture = new System.Globalization.CultureInfo(1036);
DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![Localization in ASP NET pivot tree map control](Localization_images/localization.png) 

