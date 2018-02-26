---
title: Localization | FileExplorer | ASP.NET Web | Syncfusion
description: Local culture support in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Localization
---
# Localization

The FileExplorer control provides the translations for all static texts and messages. By default the FileExplorer uses the US English (en-US) language, and it having the built-in values of all texts with the corresponding key.

The below table lists out the keys with corresponding texts in English culture.
    
    {% highlight javascript %}
    
    ej.FileExplorer.Locale["en-US"] = {
	    Back: "Backward",
        Forward: "Forward",
        Upward:"Upward",
        Refresh: "Refresh",
        Addressbar: "Address bar",
        Upload: "Upload",
        Rename: "Rename",
        Delete: "Delete",
        Download: "Download",
        Error: "Error",
        Cut: "Cut",
        Copy: "Copy",
        Paste: "Paste",
        Details: "Details",
        Searchbar: "Search bar",
        Open: "Open",
        Search: "Search",
		EmptyResult:"No items match your search",
		EmptyFolder: "This folder is empty",
        NewFolder: "New folder",
        Size: "Size",
        RenameAlert: "Please enter new name",
        NewFolderAlert: "Please enter new folder name",        
        ContextMenuOpen: "Open",
        ContextMenuNewFolder: "New folder",
        ContextMenuDelete: "Delete",
        ContextMenuRename: "Rename",
        ContextMenuUpload: "Upload",
        ContextMenuDownload: "Download",
        ContextMenuCut: "Cut",
        ContextMenuCopy: "Copy",
        ContextMenuPaste: "Paste",
        ContextMenuGetinfo: "Get info",
        ContextMenuRefresh: "Refresh",
        ContextMenuOpenFolderLocation: "Open folder location",
        Item: "item",
        Items: "items",
        Selected: "selected",
        ErrorOnFolderCreation: "This destination already contains a folder named '{0}'. Do you want to merge this folder content with already existing folder '{0}'?",
        InvalidFileName: "A file name can't contain any of the following characters: \\/:*?\"<>|",
        GeneralError: "Please see browser console window for more information",
        ErrorPath: "FileExplorer can't find '{0}'. Check the spelling and try again.",
        ReplaceAlert: "File named '{0}' already exists. Replace old file with new one?",
        DuplicateAlert: "There is already a file with the same name '{0}'. Do you want to create file with duplicate name",
        DuplicateFileCreation: "There is already a file with the same name in this location. Do you want to rename '{0}' to '{1}'?",
        DeleteFolder: " Are you sure you want to delete ",
        DeleteMultipleFolder: "Are you sure you want to delete these {0} items?",
        CancelPasteAction: "The destination folder is a subfolder of source folder.",
        OkButton: "OK",
        CancelButton: "Cancel",
        YesToAllButton: "Yes to all",
        NoToAllButton: "No to all",
        YesButton: "Yes",
        NoButton: "No",
        SkipButton:"Skip",
        Grid: "Grid view",
        Tile: "Tile view",
        LargeIcons: "Large icons",
        Name: "Name",
        Location: "Location",
        Type: "Item type",
        Layout:"Layout",
        Created: "Created",
        Accessed: "Accessed",
        Modified: "Modified",
        Permission: "Permission",
        DialogCloseToolTip: "Close",
        UploadSettings: {
            buttonText: {
                upload: "Upload",
                browse: "Browse",
                cancel: "Cancel",
                close: "Close"
            },
            dialogText: {
                title: "Upload Box",
                name: "Name",
                size: "Size",
                status: "Status"
            },
            dropAreaText: "Drop files or click to upload",
            filedetail: "The selected file size is too large. Please select a file within the valid size.",
            denyError: "Files with #Extension extensions are not allowed.",
            allowError: "Only files with #Extension extensions are allowed.",
            cancelToolTip: "Cancel",
            removeToolTip: "Remove",
            retryToolTip: "Retry",
            completedToolTip: "Completed",
            failedToolTip: "Failed",
            closeToolTip: "Close"
        }
    };
        
    {% endhighlight %}
    
## Change the Culture

The language of the FileExplorer can be changed by the “[Locale](http://help.syncfusion.com/js/api/ejfileexplorer#members:locale)” property. This property allows the culture code of the country as input. The culture code has to specify in the standard format as **[Language Code]-[County/Region Code]**.

For example the culture code for German is “**de-DE**”.

You can customize built-in text and messages based on your culture. The below example shows the usage of FileExplorer with German (de-DE) culture.
    
    {% highlight javascript %}
    
        ej.FileExplorer.Locale["de-DE"] = {
		    Back: "rückwärts",
            Forward: "Nach Vorne",
            Upward: "nach oben",
            Refresh: "erfrischen",
            Addressbar: "Adressleiste",
            Upload: "hochladen",
            Rename: "umbenennen",
            Delete: "löschen",
            Download: "herunterladen",
            Error: "Fehler",
            Cut: "Schnitt",
            Copy: "Kopie",
            Paste: "kleben",
            Details: "Einzelheiten",
            Searchbar: "Searchbar",
            Open: "geöffnet",
            Search: "Suche",
			EmptyResult: "Keine Artikel entsprechen Ihrer Suche nach",
            EmptyFolder:"Dieser Ordner ist leer",
            NewFolder: "neuer Ordner",
            SelectedFileUrl: "Web-Adresse",
            SelectedFileName: "Titel",
            ImageWidth: "Breite",
            ImageHeight: "Höhe",
            Insert: "Insert",
            Cancel: "Rückgängig Machen",
            RenameAlert: "Bitte geben Sie neuen Namen",
            NewFolderAlert: "Geben Sie den neuen Ordnernamen ein",
            ContextMenuOpen: "geöffnet",
            ContextMenuNewFolder: "Neuer Ordner",
            ContextMenuDelete: "löschen",
            ContextMenuRename: "umbenennen",
            ContextMenuUpload: "hochladen",
            ContextMenuDownload: "Herunterladen",
            ContextMenuCut: "Schnitt",
            ContextMenuCopy: "Kopie",
            ContextMenuPaste: "kleben",
            ContextMenuGetinfo: "Ausführliche Infos",
            ContextMenuRefresh: "erfrischen",
            ContextMenuOpenFolderLocation: "Öffnen Sie Ordner",
            Item: " Artikel",
            Items: " Angebote",
            Selected: "ausgewählt",
            Permission: "Erlaubnis",
            OkButton: "Ok",
            CancelButton: "Rückgängig machen",
            YesToAllButton: "Ja zu allem",
            NoToAllButton: "Nein, alle",
            YesButton: "Ja",
            NoButton: "Unterlassen Sie",
            Size: "Größe",
            Grid: "Gitter Ansicht",
            Tile: "Kachelansicht",
            LargeIcons: "Große Icons",
            Layout: "Gestaltung",
            SkipButton: "Überspringen",
            ErrorOnFolderCreation: "Dieses Ziel ist bereits ein Ordner mit dem Namen '{0}'. Möchten Sie diesen Ordner Inhalte mit bereits vorhandenen Ordner '{0}' zusammenführen möchten?",
			InvalidFileName: "Ein Dateiname darf keines der folgenden Zeichen enthalten: \\/:*?\"<>|",
            GeneralError: "Bitte beachten Sie Browser Konsolenfenster für weitere Informationen",
            ErrorPath: "Fileexplorer kann nicht finden '{0}'. Überprüfen Sie die Schreibweise und versuchen Sie es erneut.",
            ReplaceAlert: "Datei mit dem Namen '{0}' ist bereits vorhanden. Ersetzen Sie alte Datei durch eine neue?",
            DuplicateAlert: "Es gibt bereits eine Datei mit dem gleichen Namen '{0}'. Möchten Sie diese Datei mit doppelten Namen erstellen möchten",
            DuplicateFileCreation: "Es gibt bereits eine Datei mit dem gleichen Namen in diesem Ort. Möchten Sie umbenennen '{0}' bis '{1}' suchen?",
            DeleteFolder: " Sind Sie sicher, dass Sie löschen möchten ",
            DeleteMultipleFolder: "Sind Sie sicher, dass Sie diese {0} Einträge löschen?",
            CancelPasteAction: "Der Zielordner ist ein Unterordner des Quellordners.",
            Name: "Namen",
            Location: "Ort",
            Type: "Gegenstandsart",
            Created: "Erstellt",
            Modified: "geändert",
            DialogCloseToolTip: "schließen",
            UploadSettings: {
                buttonText: {
                    upload: "hochladen",
                    browse: "blättern",
                    cancel: "Rückgängig Machen",
                    close: "schließen"
                },
                dialogText: {
                    title: "hochladen Box",
                    name: "Name",
                    size: "Größe",
                    status: "Status"
                },
                cancelToolTip: "stornieren",
                removeToolTip: "entfernen",
                retryToolTip: "wiederholen",
                completedToolTip: "fertiggestellt",
                failedToolTip: "fehlgeschlagen",
                closeToolTip: "schließen"
            }
        };
            
    {% endhighlight %}
    
