---
title: Multiple Selection | FileExplorer | ASP.NET Web | Syncfusion
description: Multi selection support in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Multiple selection
---
# Multiple Selection

The FileExplorer allows the user to select multiple files by enabling the “[AllowMultiSelection](http://help.syncfusion.com/js/api/ejfileexplorer#members:allowmultiselection)” property. The multiple selection can be done by pressing the “**Ctrl”** key or “**Shift”** key. You can select all the files in the directory by pressing “**Ctrl + A**”. The multiple selection is useful on copy pasting multiple files, deleting multiple files and downloading multiple files.

In the view page, add FileExplorer element and specify the following settings to prevent multi selection.
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            AllowMultiSelection="false" 
            ShowCheckbox="false">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Checkbox option

You can enable or disable the checkbox using “**ShowCheckbox**” API of FileExplorer. Following code disables the check box only not prevents multiple selection.

In the view page, add FileExplorer element and disable the checkbox as shown below.
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/"         
            ShowCheckbox="false">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
    
    {% endhighlight %}
    
    
