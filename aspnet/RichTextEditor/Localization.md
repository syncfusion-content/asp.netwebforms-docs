---
layout: post
title: Localization with RichTextEditor | Syncfusion | ASP.NET
description: Initialize the RichTextEditor control with specified Localization  
platform: aspnet 
control: RTE
documentation: ug
keywords: RichTextEditor, Localization
---
# Localization

The editor provides option to localize its strings, it is used to adapting the editor to a particular local language. By default, the editor will use the US English (en-US) as its language. Please find the table with list of keys and their corresponding values for default language (en-US).

{% highlight js %}

ej.RTE.Locale["en-US"] = {
    
        bold: "Bold",
        italic: "Italic",
        underline: "Underline",
        strikethrough: "Strikethrough",
        superscript: "Superscript",
        subscript: "Subscript",
        justifyCenter: "Align text center",
        justifyLeft: "Align text left",
        justifyRight: "Align text right",
        justifyFull: "Justify",
        unorderedList: "Insert unordered list",
        orderedList: "Insert ordered list",
        indent: "Indent",
        fileBrowser: "File Browser",
        outdent: "Decrease Indent",
        cut: "Cut",
        copy: "Copy",
        paste: "Paste",
        paragraph: "Paragraph",
        undo: "Undo",
        redo: "Redo",
        upperCase: "Upper Case",
        lowerCase: "Lower Case",
        clearAll: "Clear All",
        clearFormat: "Clear Format",
        createLink: "Insert/Edit hyperlink",
        removeLink: "Remove hyperlink",
        image: "Insert image",
        video: "Insert video",
        editTable: "Edit Table Properties",
        embedVideo: "Paste your embed code below",
        viewHtml: "View HTML",
        fontName: "Select font family",
        fontSize: "Select font size",
        fontColor: "Select color",
        format: "Format",
        backgroundColor: "Background color",
        style: "Styles",
        deleteAlert: "Are you sure you want to clear all the contents?",
        copyPasteAlert: "Your browser doesn't support direct access to the clipboard. Please use the Ctrl+X/C/V keyboard shortcuts instead.",
        videoError: "The text area cannot be empty",
        imageWebUrl: "Web Address",
        imageAltText: "Image description",
        dimensions: "Dimensions",
        constrainProportions: "Constrain Proportions",
        linkWebUrl: "Web Address",
        imageLink: "Image as Link",
        imageBorder: "Image Border",
        imageStyle: "Style",
        linkText: "Text",
        linkToolTip: "ToolTip",
        html5Support: "This tool icon only enabled in HTML5 supported browsers",
        linkOpenInNewWindow: "Open link in new window",
        tableColumns: "No.of Columns",
        tableRows: "No.of Rows",
        tableWidth: "Width",
        tableHeight: "Height",
        tableCellSpacing: "Cell spacing",
        tableCellPadding: "Cell padding",
        tableBorder: "Border",
        tableCaption: "Caption",
        tableAlignment: "Alignment",
        textAlign: "Text align",
        dialogUpdate: "Update",
        dialogInsert: "Insert",
        dialogCancel: "Cancel",
        dialogApply: "Apply",
        dialogOk: "Ok",
        createTable: "Create table",
        addColumnLeft: "Add column on the left",
        addColumnRight: "Add column on the right",
        addRowAbove: "Add row above",
        addRowBelow: "Add row below",
        deleteRow: "Delete the row",
        deleteColumn: "Delete the column",
        deleteTable: "Delete the table",
        customTable: "Create custom table...",
        characters: "Characters",
        general: "General",
        advanced: "Advanced",
        table: "Table",
        row: "Row",
        column: "Column",
        cell: "Cell",
        solid: "Solid",
        dotted: "Dotted",
        dashed: "Dashed",
        doubled: "Doubled"
    };
    var format = [
    { text: "Paragraph", value: "p", spriteCssClass: "e-paragraph" },
    { text: "Quotation", value: "blockquote", spriteCssClass: "e-quotation" },
    { text: "Heading 1", value: "h1", spriteCssClass: "e-h1" },
    { text: "Heading 2", value: "h2", spriteCssClass: "e-h2" },
    { text: "Heading 3", value: "h3", spriteCssClass: "e-h3" },
    { text: "Heading 4", value: "h4", spriteCssClass: "e-h4" },
    { text: "Heading 5", value: "h5", spriteCssClass: "e-h5" },
    { text: "Heading 6", value: "h6", spriteCssClass: "e-h6" }
    ];

{% endhighlight %}

N>  The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the editor’s strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the editor in German language (“de-DE”).

{% highlight js %}

ej.RTE.Locale["de-DE"] = {
        
        bold: "fett",
        italic: "kursiv",
        underline: "unterstreichen",
        strikethrough: "Durchgestrichen",
        superscript: "Hochgestellt ",
        subscript: "Tiefgestellt",
        justifyCenter: "Ausrichten von Text Zentrum",
        justifyLeft: "Ausrichten von Text links",
        justifyRight: "Ausrichten von Text rechts",
        justifyFull: "rechtfertigen",
        unorderedList: "Legen Sie ungeordnete Liste",
        orderedList: "Geordnete Liste einfügen ",
        indent: "Gedankenstrich",
        fileBrowser: "Datei-Browser",
        outdent: "Einzug verkleinern",
        cut: "Cut",
        copy: "Kopie",
        paste: "Paste",
        paragraph: "Absatz",
        undo: "rückgängig machen",
        redo: "wiederholen",
        upperCase: "Großbuchstaben",
        lowerCase: "Kleinbuchstaben",
        clearAll: "Alles löschen",
        clearFormat: "Klar Format",
        createLink: "Einfügen / bearbeiten Hyperlink",
        removeLink: "Hyperlink entfernen",
        image: "Bild einfügen",
        video: "Video einfügen",
        editTable: " Table Edit Properties",
        embedVideo: "Fügen Sie Ihren Code einbetten unten",
        viewHtml: "View HTML",
        fontName: "Wählen Sie Schriftfamilie",
        fontSize: "Schriftgröße wählen",
        fontColor: "Farbe wählen",
        format: "formatieren",
        backgroundColor: "Hintergrundfarbe",
        style: "Styles",
        deleteAlert: "Sind Sie sicher, dass Sie den gesamten Inhalt löschen?",
        copyPasteAlert: "Ihr Browser unterstützt keine direkten Zugriff auf die Zwischenablage. Bitte verwenden Sie stattdessen die Strg + X / C / V Tastenkombinationen",
        videoError: "Der Textbereich kann nicht leer sein",
        imageWebUrl: "Webadresse",
        imageAltText: "Bildbeschreibung",
        dimensions: "Abmessungen",
        constrainProportions: "Proportionen beschränken",
        linkWebUrl: "Webadresse",
        imageLink: "Bild als Link-",
        imageBorder: "Bild Rand",
        imageStyle: "Stil",
        linkText: "Text",
        linkToolTip: "Tooltip",
        html5Support: "Dieses Werkzeug-Symbol in HTML5 ist nur aktiviert, unterstützten Browser",
        linkOpenInNewWindow: "Link in neuem Fenster öffnen",
        tableColumns: "Keine der Spalten",
        tableRows: "Keine der Zeilen",
        tableWidth: "Weite",
        tableHeight: "Höhe",
        tableCellSpacing: "Zellenabstand",
        tableCellPadding: "Zellauffüllung",
        tableBorder: "Border",
        tableCaption: "Bildunterschrift",
        tableAlignment: "Ausrichtung",
        textAlign: "Text align",
        dialogUpdate: "aktualisieren",
        dialogInsert: "Insert",
        dialogCancel: "Absagen",
        dialogApply: "Bewerben",
        dialogOk: "Ok",
        createTable: "create table",
        addColumnLeft: "Spalte hinzufügen an der linken",
        addColumnRight: "Spalte hinzufügen am rechten",
        addRowAbove: "In Zeile über",
        addRowBelow: "Zeile hinzufügen unter",
        deleteRow: "Löschen Sie die Zeile",
        deleteColumn: "Löschen Sie die Spalte",
        deleteTable: "Löschen Sie die Tabelle",
        customTable: "Erstellen Sie benutzerdefinierte Tabelle ...",
        characters: "Charaktere",
        general: "Allgemein",
        advanced: "Erweiterte",
        table: "Tabelle",
        row: "Zeile",
        column: "Spalte",
        cell: "Zelle",
        solid: "solide",
        dotted: "gepunktete",
        dashed: "Eine gestrichelte",
        doubled: "verdoppelt",
        maximize: "maximieren",
        resize: "minimieren",
        swatches: "Farbfelder"
    };
    
{% endhighlight %}

You can set the Locale property of the editor to the new language. 

{% highlight html %}

      <ej:RTE ID="RTE1" Locale="de-DE" runat="server">
            <RTEContent>
                 Description:
                    <p> The Rich Text Editor (RTE) control is an easy to render in
                    client side. Customer easy to edit the contents and get the HTML content for
                    the displayed content. A rich text editor control provides users with a toolbar
                    that helps them to apply rich text formats to the text entered in the text
                    area. </p>
            </RTEContent>
        <Format>
            <ej:Format Text="Absatz" Value="p" SpriteCssClass="e-paragraph" />
            <ej:Format Text="Zitat" Value="blockquote" SpriteCssClass="e-quotation" />
            <ej:Format Text="Kopf 1" Value="h1" SpriteCssClass="e-h1" />
            <ej:Format Text="Kopf 2" Value="h2" SpriteCssClass="e-h12" />
            <ej:Format Text="Kopf 3" Value="h3" SpriteCssClass="e-h3" />
            <ej:Format Text="Kopf 4" Value="h4" SpriteCssClass="e-h4" />
            <ej:Format Text="Kopf 5" Value="h5" SpriteCssClass="e-h5" />
            <ej:Format Text="Kopf 6" Value="h6" SpriteCssClass="e-h6" />
        </Format>
           
    </ej:RTE>
        
{% endhighlight %}