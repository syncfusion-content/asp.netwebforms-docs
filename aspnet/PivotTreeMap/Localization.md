---
layout: post
title: Localization | PivotTreeMap | ASP.NET | Syncfusion
description: localization 
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# Localization

## Localization and Globalization of Cube Info (Client Mode)

Content displayed within the PivotTreeMap control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.

* To get localized data from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture in the **"data"** property present inside **"dataSource"**. 

{% highlight js %}

//1036 refers to “fr-FR” culture.
<ej:PivotTreeMap ID="PivotTreeMap1" runat="server" IsResponsive="true" ClientIDMode="Static">
  <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll; Locale Identifier=1036;">
     //...
  </DataSource>
</ej:PivotTreeMap>

{% endhighlight %}

## Localization and Globalization of Cube Info (Server Mode)

Content displayed within the PivotTreeMap control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.

* To get the localized string based on different cultures, from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture. 
* To bind the globalized content in PivotTreeMap control, we need to set **"Culture"** and **"OverrideDefaultFormatStrings"** properties in OlapDataManager class to a specific culture. 
 
{% highlight c# %}

//1036 refers to “fr-FR” culture.
string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
DataManager = new OlapDataManager(connectionString);
DataManager.Culture = new System.Globalization.CultureInfo(1036);
DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![](Localization_images/localization.png) 

