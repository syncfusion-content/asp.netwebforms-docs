---
layout: post
title: Localization-and-Translation-Support
description: localization and translation support
platform: aspnet
control: OLAP Gauge
documentation: ug
---

# Localization and Translation Support

Localization is the process of customizing the user interface (UI) as locale-specific in order to display regional data.
Using this feature, you can display the data in a specific language and culture, of a particular country or region. 
The ASP.NET OlapGauge control provides inherent support to localize its UI.

The following table lists the default English localization User Interface based on French culture.



Table: List of default English localization User Interface based on French culture



<table>
<tr>
<th>
KEYWORDS</th><th>
VALUES</th></tr>
<tr>
<td>
RevenueGoal</td><td>
"Revenu Objectifs",</td></tr>
<tr>
<td>
RevenueValue</td><td>
"Revenu Valeurs",</td></tr>
<tr>
<td>
RevenueFor</td><td>
"Revenu Pour",</td></tr>
<tr>
<td>
MDXqueryExecutionFailed</td><td>
"L'exécution de la requête MDX pas",</td></tr>
<tr>
<td>
PreparingAndExecutingMDXquery</td><td>
"Préparation et exécution d'une Requête MDX",</td></tr>
<tr>
<td>
MDXqueryExecutedSuccessfully</td><td>
"Requête MDX exécutée avec succès",</td></tr>
<tr>
<td>
RenderingStarted</td><td>
"Rendu en route",</td></tr>
<tr>
<td>
RenderingSucceeded</td><td>
"Rendu Réussi",</td></tr>
<tr>
<td>
RenderingFailed</td><td>
"Rendant pas"</td></tr>
</table>


The following code example illustrates you on how to localize OlapGuage’s User Interface (UI) based on “French” culture.




{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent" Locale="fr-FR">

        <Scales>

            <ej:CircularScales ShowRanges="true" Radius="150" ShowScaleBar="true" Size="1"  ShowIndicators="true" ShowLabels="true" >

                <Border Width ="0.5" />

                <PointerCollection>                    

                    <ej:Pointers Type="Needle" ShowBackNeedle="true" BackNeedleLength="20"  Length="120" Width="7" NeedleType="Triangle" ></ej:Pointers>

                    <ej:Pointers Type="Marker" MarkerType="Diamond" DistanceFromScale="5" Placement="Center" BackgroundColor="#29A4D9" Length="25" Width="15"></ej:Pointers>

                </PointerCollection>

                <TickCollection>

                    <ej:CircularTicks Type="Major" DistanceFromScale="15" Height="16" Width="1" Color="#8c8c8c" />

                    <ej:CircularTicks Type="Minor" DistanceFromScale="2" Height="6" Width="1" Color="#8c8c8c" />

                </TickCollection>

                <LabelCollection>

                    <ej:CircularLabels Color="#8c8c8c"></ej:CircularLabels>

                </LabelCollection>

                <RangeCollection>

                    <ej:CircularRanges DistanceFromScale="-10" BackgroundColor="black" Size="7">

                        <Border Color="red"/></ej:CircularRanges>

                    <ej:CircularRanges DistanceFromScale="-10" Size="7"></ej:CircularRanges>

                </RangeCollection>

                <CustomLabelCollection>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="290" />

                        <Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="320" />

                        <Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="150" />

                        <Font Size="12px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                </CustomLabelCollection>   

            </ej:CircularScales>

        </Scales>

    </ej:OlapGauge>

</asp:Content>

{% endhighlight %}



{% highlight html %}

<asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection">

    <script type="text/javascript">

        ej.olap.OlapGauge.locale["fr-FR"] = {

            RevenueGoal: "Objectif de chiffre d'affaires",

            RevenueValue: "Valeur du chiffre d'affaires",

            RevenueFor: "Recettes pour",

            MDXqueryExecutionFailed: "L'exécution de la requête MDX pas",

            PreparingAndExecutingMDXquery: "La préparation et l'exécution de la requête MDX",

            MDXqueryExecutedSuccessfully: "MDX requête exécutée avec succès",

            RenderingStarted: "Rendu commencé",

            RenderingSucceeded: "Rendu réussi",

            RenderingFailed: "Rendant pas"

        }

    </script>

</asp:Content>

{% endhighlight %}


 

N> In order to render the localized OLAP Gauge, You are required to reset the content available in both 1. OLAP Gauge Control 2. OLAP Cube

## Localizing Control Information:

To apply control side localization, refer the following code example:



{% highlight js %}

ej.olap.OlapGauge.locale["zh-CN"] = {

//Corresponding keyword values needs to be set here.

}


{% endhighlight %}

## Localizing Cube Information:

To render the localized Cube information,set “_Locale__Identifier”___in the connection string.




{% highlight C# %}

//1036 refers to “fr-FR” culture.

string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";

DataManager = new OlapDataManager(connectionString);

DataManager.Culture = new System.Globalization.CultureInfo(1036);

DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight  %}

The following screenshot displays the OlapGauge with French localization.

![](Localization-and-Translation-Support_images/Localization-and-Translation-Support_img2.png) 



