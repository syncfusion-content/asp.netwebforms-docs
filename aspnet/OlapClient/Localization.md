---
layout: post
title: Localization
description: localization 
platform: aspnet
control: OLAP Client
documentation: ug
---

# Localization 

Localization is theprocess of customizing the UI (User Interface) as locale-specific, in order to display regional data. Using this feature, data can be displayed in a specific language and culture, of a particular country or region. The ASP.NET OLAP Client control provides inherent support to localize its UI.

The following table lists the default English localization User Interface based on French culture.

_Table: List of default English localization User Interface based on French culture_

<table>
<tr>
<th>
KEYWORDS</th><th>
VALUES</th></tr>
<tr>
<td>
Column</td><td>
"Colonne “</td></tr>
<tr>
<td>
Row</td><td>
"Rangée"</td></tr>
<tr>
<td>
Slicer</td><td>
"tranche"</td></tr>
<tr>
<td>
CubeSelector</td><td>
"Sélecteur de Cube",</td></tr>
<tr>
<td>
ReportName</td><td>
"Nom du rapport",</td></tr>
<tr>
<td>
NewReport</td><td>
"Nouveau rapport",</td></tr>
<tr>
<td>
CubeDimensionBrowser</td><td>
"Cube navigateur dimnesion",</td></tr>
<tr>
<td>
AddReport</td><td>
"Ajouter un rapport",</td></tr>
<tr>
<td>
RemoveReport</td><td>
"Retirer rapport",</td></tr>
<tr>
<td>
CannotRemoveSingleReport</td><td>
"Vous ne pouvez pas supprimer Rapport unique",</td></tr>
<tr>
<td>
AreYouSureToDeleteTheReport</td><td>
"Etes-vous sûr de vouloir supprimer le rapport",</td></tr>
<tr>
<td>
RenameReport</td><td>
"Renommer rapport",</td></tr>
<tr>
<td>
SaveReport</td><td>
"Enregistrer le rapport",</td></tr>
<tr>
<td>
LoadReport</td><td>
"Rapport de charge",</td></tr>
<tr>
<td>
ExportToExcel:</td><td>
"Exporter vers Excel",</td></tr>
<tr>
<td>
FullScreen</td><td>
"Plein écran",</td></tr>
<tr>
<td>
Grid</td><td>
"Grille",</td></tr>
<tr>
<td>
Chart</td><td>
"Graphiq",</td></tr>
<tr>
<td>
OK</td><td>
"Bien",</td></tr>
<tr>
<td>
Cancel</td><td>
"Annuler",</td></tr>
<tr>
<td>
MeasureEditor</td><td>
"Mesurer éditeur",</td></tr>
<tr>
<td>
MemberEditor:</td><td>
"Sous la direction de membres",</td></tr>
<tr>
<td>
Measures</td><td>
"Mesures",</td></tr>
<tr>
<td>
OpeningDialog</td><td>
"Dialogue d'ouverture",</td></tr>
<tr>
<td>
OpeningDialogSucceeded</td><td>
"Dialogue d'ouverture réussi",</td></tr>
<tr>
<td>
PreparingAndExecutingMDXquery</td><td>
"la préparation et l'exécution de la requête MDX"</td></tr>
<tr>
<td>
MDXqueryExecutionFailed</td><td>
"L'exécution de la requête MDX pas",</td></tr>
<tr>
<td>
MDXqueryExecutedSuccessfully</td><td>
"MDX requête exécutée avec succès"</td></tr>
<tr>
<td>
RenderingLayoutStarted</td><td>
"Disposition rendant commencé",</td></tr>
<tr>
<td>
RenderingLayoutCompleted,</td><td>
" Disposition rendant terminé",</td></tr>
<tr>
<td>
RenderingStarted</td><td>
"Rendu commencé",</td></tr>
<tr>
<td>
RenderingSucceeded</td><td>
"Rendu Réussi",</td></tr>
<tr>
<td>
SortOrFilterColumn</td><td>
" Tri/filtrage (colonne)",</td></tr>
<tr>
<td>
SortOrFilterRow</td><td>
"Tri/filtrage (ligne)",</td></tr>
<tr>
<td>
SortingAndFiltering</td><td>
" Trier et filtrer",</td></tr>
<tr>
<td>
Sorting</td><td>
" Tri",</td></tr>
<tr>
<td>
Measure</td><td>
" Mesurer",</td></tr>
<tr>
<td>
Order</td><td>
" ordre",</td></tr>
<tr>
<td>
Filtering</td><td>
" Filtrage",</td></tr>
<tr>
<td>
Condition</td><td>
" Condition ",</td></tr>
<tr>
<td>
Value</td><td>
" Valeur ",</td></tr>
<tr>
<td>
PreserveHierarchy</td><td>
" Préserver hiérarchie ",</td></tr>
<tr>
<td>
Ascending</td><td>
" Croissant ",</td></tr>
<tr>
<td>
Descending</td><td>
" Descendant ",</td></tr>
<tr>
<td>
Enable</td><td>
" Permettre ",</td></tr>
<tr>
<td>
Disable</td><td>
" Désactiver ",</td></tr>
<tr>
<td>
And</td><td>
" et "</td></tr>
</table>


The following code example shows how to localize OLAP Client’s User Interface (UI) based on French culture.

{% highlight html %}

<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Locale="fr-FR">

</ej:OlapClient>

{% endhighlight  %}


{% highlight html%}  

<script type="text/javascript">

    {

       ej.olap.OlapClient.locale["fr-FR"] = {

            Column: "Colonne",

            Row: "Rangée",

            Slicer: "tranche",

            CubeSelector: "Sélecteur de Cube",

            ReportName: "Nom du rapport",

            NewReport: "nouveau rapport",

            CubeDimensionBrowser: "Cube navigateur dimnesion",

            AddReport: "Ajouter un rapport",

            RemoveReport: "Retirer rapport",

            CannotRemoveSingleReport: "Vous ne pouvez pas supprimer Rapport unique",

            AreYouSureToDeleteTheReport: "Etes-vous sûr de vouloir supprimer le rapport",

            RenameReport: "Renommer rapport",

            SaveReport: "Enregistrer le rapport",

            LoadReport: "Rapport de charge",

            ExportToExcel: "Exporter vers Excel",

            FullScreen: "Plein écran",

            Grid: "Grille",

            Chart: "Graphiq",

            OK: "bien",

            Cancel: "Annuler",

            MeasureEditor: "Mesurer éditeur",

            MemberEditor: "Sous la direction de membres",

            Measures: "Mesures",

            OpeningDialog: "Dialogue d'ouverture",

            OpeningDialogSucceeded: "Dialogue d'ouverture réussi",

            RenderingLayoutStarted: "Disposition rendant commencé",

            RenderingLayoutCompleted: "disposition rendant terminé",

            MDXqueryExecutionFailed: "L'exécution de la requête MDX pas",

            PreparingAndExecutingMDXquery: "la préparation et l'exécution de la requête MDX",

            MDXqueryExecutedSuccessfully: "MDX requête exécutée avec succès",

            RenderingStarted: "Rendu commencé",

            RenderingSucceeded: "Rendu Réussi",

            RenderingFailed: "Rendant pas",

            SortOrFilterColumn: " tri/filtrage (colonne)",

            SortOrFilterRow: "tri/filtrage (ligne)",

            SortingAndFiltering: " trier et filtrer",

            Sorting: " Tri",

            Measure: "mesurer",

            Order: "Ordre",

            Filtering: "Filtrage",

            Condition: " condition ",

            Value: " valeur ",

            PreserveHierarchy: " préserver hiérarchie ",

            Ascending: "Croissant ",

            Descending: "Descendant ",

            Enable: " Permettre ",

            Disable: " Désactiver ",

            and: "et "

            }

       ej.olap.OlapChart.locale["fr-FR"] = {

            Row: "Rangée",

            Column: "Colonne",

            Value: "Valeur",

            Expand: "Développer",

            Collapse: "Effondrement",

            Exit: "Quitter"

          }       

  }

 </script>           

{% endhighlight  %}



> Note: In order to render the localized OLAP Client, we need to reset the content available in both OLAP Client Control and OLAP Cube

## Localizing Control Information

To apply control side localization, use the following code example.


{% highlight js %}

 ej.olap.OlapClient.locale["zh-CN"] = {

//Corresponding keyword values needs to be set here.

}


{% endhighlight %}

## Localizing Cube Information

To get the localized Cube information, set LocaleIdentifier__in the connection string.



{% highlight C# %}

//1036 refers to“fr-FR” culture.

string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";

DataManager = new OlapDataManager(connectionString);

DataManager.Culture = new System.Globalization.CultureInfo(1036);

DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight  %}


The following screenshot shows the OLAP Client with French localization.

![Description: http://help.syncfusion.com/ug/js/ImagesExt/image49_140.png](Localization_images/Localization_img2.png) 
