---
layout: post
title: Localization
description: localization
platform: aspnet
control: PivotGrid
documentation: ug
---

## Localization

> _Note:__This feature is currently not applicable for PivotTable Field List._

Localization is the process of customizing the user interface (UI) as locale-specific in order to display regional data. Using this feature, data is displayed in a specific language and culture of a particular country or region. The ASP.NETPivotGrid control provides inherent support to localize its UI.The following table lists the default English localization user interface based on French culture. 

_List of default English localization user interface based on French culture_

<table>
<tr>
<td>
Keyword</td><td>
Values</td></tr>
<tr>
<td>
SeriesPage</td><td>
“Series Page”</td></tr>
<tr>
<td>
CategoricalPage</td><td>
"Page catégorique"</td></tr>
<tr>
<td>
MDXqueryExecutionFailed</td><td>
"L'exécution de la requête MDX pas"</td></tr>
<tr>
<td>
PreparingAndExecutingMDXquery</td><td>
"la préparation et l'exécution de la requête MDX"</td></tr>
<tr>
<td>
MDXqueryExecutedSuccessfully</td><td>
"MDX requête exécutée avec succès"</td></tr>
<tr>
<td>
RenderingStarted:</td><td>
"Rendu commencé",</td></tr>
<tr>
<td>
RenderingSucceeded</td><td>
"Rendu réussi",</td></tr>
<tr>
<td>
RenderingFailed</td><td>
"Rendant pas"</td></tr>
</table>


The following code example illustrates how to localize PivotGrid’s user interface based on “French” culture.



[ASP.NET] 

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

    &lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Locale="fr-FR"&gt;&lt;/ej:PivotGrid&gt;

&lt;/asp:Content&gt;



&lt;asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

     &lt;script type="text/javascript"&gt;

         ej.PivotGrid.locale["fr-FR"] = {

             SeriesPage: "Série Page",

             CategoricalPage: "Catégorique Page",

             MDXqueryExecutionFailed: "L'exécution de la requête MDX pas",

             PreparingAndExecutingMDXquery: "la préparation et l'exécution de la requête MDX",

             MDXqueryExecutedSuccessfully: "MDX requête exécutée avec succès",

             RenderingStarted: "Rendu commencé",

             RenderingSucceeded: "Rendu réussi",

             RenderingFailed: "Rendant pas"

         };

         ej.PivotPager.locale["fr-FR"] = {

             SeriesPage: "Série Page",

             CategoricalPage: "Catégorique Page",

         };

     &lt;/script&gt;

&lt;/asp:Content&gt;





_Note: In order to render the localized PivotGrid, you can reset the content available in both_

1. _OLAP Grid Control_
2. _OLAP Cube_

Localizing Control Information: 

To apply control side Localization, you can refer the following code example.

[HTML]

ej.PivotGrid.locale["zh-CN"] = {

//Corresponding keyword values needs to be set here.

} 

Localizing Cube Information

To get the LocalizedCubeInformation, “_Locale__Identifier__"_ is set in the connection string



[C#]

//1036 refers to “fr-FR” culture.

string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";

DataManager = new OlapDataManager(connectionString);

DataManager.Culture = new System.Globalization.CultureInfo(1036);

DataManager.OverrideDefaultFormatStrings = true;



The following screenshot displays the PivotGrid with French localization:

{ ![](Localization_images/Localization_img1.png) | markdownify }
{:.image }


_Localized PivotGrid_

