---
layout: post
title: Localization | Gantt | ASP.NET Webforms | Syncfusion
description: localization
platform: aspnet
control: Gantt
documentation: ug
---

# Localization

Localization is the process of customizing the User Interface (UI) based on a culture, specific to a particular country or region, in order to display regional data. The culture is represented by a unique string like `en``-``US` for US English and `fr``-``FR` for French.

Localization is the key feature that provides solutions to global customers with the help of localized control. It is necessary to include the specific culture script files (ej.culture.fr-FR.min.js file for French culture) in the reference section, which is available in the following location.

`(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n`

Also it is possible to localize all the texts in the Gantt control with specific culture by referring the ej.localetexts.fr-FR.min.js file which is available in the following location.

`(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i10n`

The following code example explains on how to localize the control in French culture

{% highlight javascript %}

<head>

//…

<script src="Scripts/ej.culture.fr-FR.min.js"></script>

<script src="Scripts/ej.localetexts.fr-FR.js"></script>

</head>

<ej:Gantt ID="GanttContainer" runat="server" Locale="fr-FR"> </ej:Gantt>

{% endhighlight %}

![](Localization_images/Localization_img2.png)

Which will localize all the text and date formats to French culture. If we still need to customize the localized text, we can define them locally in the sample as explained below.

{% highlight javascript %}

<ej:Gantt ID="GanttContainer" runat="server" Locale="fr-FR"></ej:Gantt>

<script type="text/javascript">

    <script type = "text/javascript">

    ej.Gantt.Locale["fr-FR"] = {

        emptyRecord: "Aucun enregistrement à afficher",

        alertTexts: {

            indentAlert: "Il n'y a aucune trace de Gantt est sélectionné pour effectuer le retrait",

            outdentAlert: "Il n'y a aucune trace de Gantt est sélectionné pour effectuer le retrait négatif",

            predecessorEditingValidationAlert: "Cyclique dépendance survenu, S'il vous plaît Consultez le prédécesseur",

            predecessorAddingValidationAlert: "Remplissez toutes les colonnes dans la table prédécesseur",

            idValidationAlert: "Duplicate ID",

            dateValidationAlert: "Invalid Date de fin",

            dialogResourceAlert: "Remplissez toutes les colonnes du tableau des ressources"

        },

        //headerText to be displayed in TreeGrid 

        columnHeaderTexts: {

            taskId: "Tâche Ia",

            taskName: "Tâche Tâche",

            startDate: "Démarrer Date",

            endDate: "Fin Date",

            resourceInfo: "Ressources",

            duration: "Durée",

            status: "Progrès",

            predecessor: "Prédécesseur",

            baselineStartDate: "Baseline Démarrer Date",

            baselineEndDate: "Baseline Fin Date"

        },

        //string to display in dialog 

        editDialogTexts: {

            addFormTitle: "Nouveau Tâche",

            editFormTitle: "Modifier Tâche",

            saveButton: "Sauver",

            cancelButton: "Annuler"

        },

        columnDialogTexts: {

            field: "Champ",

            headerText: "En-tête",

            editType: "Modifier le type",

            filterEditType: "Modifier le type de filtre",

            allowFiltering: "Autoriser le filtrage",

            allowFilteringBlankContent: "Autoriser le filtrage du contenu Blank",

            allowSorting: "Autoriser tri",

            visible: "Visible",

            width: "Largeur",

            textAlign: "Alignement du texte",

            headerTextAlign: "Alignement du texte en-tête",

            columnsDropdownData: "Colonne Chute de données vers le bas",

            dropdownTableText: "Texte",

            dropdownTableValue: "Valeur",

            addData: "Ajouter",

            deleteData: "Retirer",

            allowCellSelection: "Autoriser la sélection de cellules",

            clipMode: "Mode Clip",

            tooltip: "Info-bulle",

            headerTooltip: "Header Tooltip"

        },

        editTypeTexts: {

            string: "Chaîne",

            numeric: "Numérique",

            datePicker: "Sélecteur de date",

            dateTimePicker: "Date Time Picker",

            dropdown: "Menu déroulant",

            boolean: "Boolean"

        },

        textAlignTypes: {

            right: "Droite",

            left: "La gauche",

            center: "centre"

        },

        clipModeTexts: {

            clip: "Agrafe",

            ellipsis: "Ellipse"

        },

        toolboxTooltipTexts: {

            addTool: "Ajouter",

            editTool: "modifier",

            saveTool: "Mettre à jour",

            deleteTool: "Effacer",

            cancelTool: "Annuler",

            searchTool: "Chercher",

            indentTool: "tiret",

            outdentTool: "Retrait négatif",

            expandAllTool: "Développer tout",

            collapseAllTool: "Réduire tout",

            nextTimeSpanTool: "Suivant Timespan",

            prevTimeSpanTool: "Précédent Timespan",

            criticalPathTool: "Chemin critique",

            excelExportTool: "Exportation Excel",

            pdfExportTool: "Exportation PDF"

        },

        durationUnitTexts: {

            days: "journées",

            hours: "heures",

            minutes: "minutes",

            day: "journée",

            hour: "heure",

            minute: "minute"

        },

        durationUnitEditText: {

            minute: ["m", "min", "minute", "minutes"],

            hour: ["h", "heure", "heure", "heures"],

            day: ["ré", "dy", "journée", "journées"]

        },

        workUnitTexts: {

            days: "journées",

            hours: "heures",

            minutes: "minutes"

        },

        taskTypeTexts: {

            fixedWork: "travail fixe",

            fixedUnit: "Unités fixes",

            fixedDuration: "Durée fixe"

        },

        effortDrivenTexts: {

            yes: "Oui",

            no: "Non"

        },

        contextMenuTexts: {

            taskDetailsText: "Détails de la tâche ...",

            addNewTaskText: "Ajouter une nouvelle tâche",

            indentText: "tiret",

            outdentText: "Retrait négatif",

            deleteText: "Effacer",

            aboveText: "Au dessus de",

            belowText: "Au dessous de"

        },

        newTaskTexts: {

            newTaskName: "Nouvelle tâche"

        },

        columnMenuTexts: {

            sortAscendingText: "Trier par ordre croissant",

            sortDescendingText: "Trier par ordre décroissant",

            columnsText: "colonnes",

            insertColumnLeft: "Insérez la colonne de gauche",

            insertColumnRight: "Insérez la colonne de droite",

            deleteColumn: "Supprimer la colonne",

            renameColumn: "Renommer la colonne"

        },

        taskModeTexts: {

            manual: "Manuel",

            auto: "Auto"

        },

        columnDialogTitle: {

            insertColumn: "Insérer une colonne",

            deleteColumn: "Supprimer la colonne",

            renameColumn: "Renommer la colonne"

        },

        deleteColumnText: "Êtes-vous sûr de vouloir supprimer cette colonne?",

        okButtonText: "D'accord",

        cancelButtonText: "Annuler",

        confirmDeleteText: "Confirmation de la suppression",

        predecessorEditingTexts: {

            fromText: "De",

            toText: "À"

        },

        dialogTabTitleTexts: {

            generalTabText: "Général",

            predecessorsTabText: "Prédécesseurs",

            resourcesTabText: "Ressources",

            customFieldsTabText: "Les champs personnalisés",

            notesTabText: "Remarques"

        },

        predecessorCollectionText: [{

                id: "SS",

                text: "Démarrer-Démarrer",

                value: "Démarrer-Démarrer"

            },

            {

                id: "SF",

                text: "Démarrer-terminer",

                value: "Démarrer-terminer"

            },

            {

                id: "FS",

                text: "terminer-Démarrer",

                value: "terminer-Démarrer"

            },

            {

                id: "FF",

                text: "terminer-terminer",

                value: "terminer-terminer"

            }

        ],

    }

</script>



{% endhighlight %}

![](Localization_images/Localization_img1.png)

## Date format

The default date format used in the Gantt control is “MM/dd/yyyy”. Date formats will be changed based on the culture referred in the control. But if you still need to change the date format we can define the desired format using the dateFormat property. The same have been explained in the following code example.

{% highlight javascript %}

<ej:Gantt ID="GanttContainer" runat="server" DateFormat="dd/MM/yyyy" Locale="fr-FR">

    <ScheduleHeaderSettings WeekHeaderFormat="dd/MM/yyyy" />

</ej:Gantt>

{% endhighlight %}

![](Localization_images/Localization_img3.png)

