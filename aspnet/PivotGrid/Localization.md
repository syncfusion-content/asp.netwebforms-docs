---
layout: post
title: Localization
description: localization
platform: aspnet
control: PivotGrid
documentation: ug
---

# Localization

> Note: This feature is currently not applicable for PivotTable Field List.

Localization is the process of customizing the user interface (UI) as locale-specific in order to display regional data. Using this feature, data is displayed in a specific language and culture of a particular country or region. The ASP.NETPivotGrid control provides inherent support to localize its UI.The following table lists the default English localization user interface based on French culture. 

List of default English localization user interface based on French culture


<table>
<tr>
<th>
Keyword</th><th>
Values</th></tr>
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


{% highlight html %}


<asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection">

    <ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Locale="fr-FR"></ej:PivotGrid>

</asp:Content>

<asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection">

     <script type="text/javascript">

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

     </script>

</asp:Content>

{% endhighlight %}


> Note: In order to render the localized PivotGrid, you can reset the content available in both
>
> 1. OLAP Grid Control
> 2. OLAP Cube

### Localizing Control Information: 

To apply control side Localization, you can refer the following code example.

{% highlight js %}


ej.PivotGrid.locale["zh-CN"] = {

//Corresponding keyword values needs to be set here.

} 

{% endhighlight %}

### Localizing Cube Information

To get the LocalizedCubeInformation, “Locale Identifier" is set in the connection string


{% highlight C# %}


//1036 refers to “fr-FR” culture.

string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";

DataManager = new OlapDataManager(connectionString);

DataManager.Culture = new System.Globalization.CultureInfo(1036);

DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}


The following screenshot displays the PivotGrid with French localization:

 ![](Localization_images/Localization_img1.png) 

_Localized PivotGrid_