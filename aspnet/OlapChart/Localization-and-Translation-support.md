---
layout: post
title: Localization-and-Translation-support
description: localization and translation support
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Localization and Translation support

Localization is the process of customizing the user interface (UI) as locale-specific in order to display regional data. Using this feature, data is displayed in a language and culture specific to a particular country or region. The ASP.NET OlapChart control provides inherent support to localize its UI.

The following table lists the default English localizationUserInterface based on “French” culture.

Table: List of default English localization User Interface based on “French” culture

<table>
<tr>
<td>
{{ '**KEYWORDS**' | markdownify }}</td><td>
{{ '**VALUES**' | markdownify }}</td></tr>
<tr>
<td>
Measure</td><td>
“Mesure”</td></tr>
<tr>
<td>
Row</td><td>
"Rangée "</td></tr>
<tr>
<td>
Column</td><td>
"Colonne”</td></tr>
<tr>
<td>
Value</td><td>
" Valeur "</td></tr>
<tr>
<td>
Expand</td><td>
" Développer "</td></tr>
<tr>
<td>
Collapse</td><td>
" Effondrement "</td></tr>
<tr>
<td>
Exit</td><td>
“Quitter "</td></tr>
<tr>
<td>
MDXqueryExecutionFailed</td><td>
"L'exécution de la requête MDX pas "</td></tr>
<tr>
<td>
PreparingAndExecutingMDXquery</td><td>
"La préparation et l'exécution de la requête MDX "</td></tr>
<tr>
<td>
MDXqueryExecutedSuccessfully</td><td>
" MDX requête exécutée avec succès "</td></tr>
<tr>
<td>
RenderingSucceeded</td><td>
“Rendu réussi "</td></tr>
<tr>
<td>
RenderingStarted</td><td>
“Rendu commencé ",</td></tr>
<tr>
<td>
RenderingFailed</td><td>
"Rendant pas "</td></tr>
</table>


The following code example shows how to localize OlapChart’sUser Interface (UI) based on “French” culture.

{% highlight html %}

[ASP.NET]

<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Locale="fr-FR">

    </ej:OlapChart>

</asp:Content>



<asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection">

<script type="text/javascript">

    ej.olap.OlapChart.locale["fr-FR"] = {

        Measure: "Mesurer ",

        Row: "Rangée",

        Column: "Colonne",

        Value: "Valeur",

        Expand: "Développer",

        Collapse: "Effondrement",

        Exit: "Quitter",

        MDXqueryExecutionFailed: "L'exécution de la requête MDX pas",

        PreparingAndExecutingMDXquery: "La préparation et l'exécution de la requête MDX",

        MDXqueryExecutedSuccessfully: "MDX requête exécutée avec succès",

        RenderingStarted: "Rendu commencé",

        RenderingSucceeded: "Rendu réussi",

        RenderingFailed: "Rendant pas"

    };

</script>   

</asp:Content> 

{% endhighlight %}

![C:/Users/labuser/Desktop/note.jpg](Localization-and-Translation-support_images/Localization-and-Translation-support_img1.jpeg)

Note: In order to render the localized OLAP Chart, you are required to reset the content available in both

1. OLAP Chart Control

2. OLAP Cube

## Localizing Control Information:

To apply control side localization, refer the following code example:

{% highlight html %}

[HTML]

ej.olap.OlapChart.locale["zh-CN"] = {

//Corresponding keyword values needs to be set here.

}

{% endhighlight %}

## Localizing Cube Information:

To get the localized Cube information, “_Locale__Identifier"_ has to be set in the connection string:

{% highlight c# %}

[C#]

//1036 refers to “fr-FR” culture.

string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";

DataManager = new OlapDataManager(connectionString);

DataManager.Culture = new System.Globalization.CultureInfo(1036);

DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

The output for the LocalizedOlapChart is as follows:

![C:/Users/labuser/Desktop/a.png](Localization-and-Translation-support_images/Localization-and-Translation-support_img2.png) 



