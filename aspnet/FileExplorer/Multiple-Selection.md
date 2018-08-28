---
title: Multiple Selection | FileExplorer | ASP.NET Web | Syncfusion
description: Multi selection support in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Multiple selection
---
# Multiple Selection

The FileExplorer allows the user to select multiple files by enabling the “[AllowMultiSelection](http://help.syncfusion.com/js/api/ejfileexplorer#members:allowmultiselection)” property. The multiple selection can be done by pressing the “**Ctrl”** key or “**Shift”** key. You can select all the files in the directory by pressing “**Ctrl + A**”. The multiple selection is useful on copy pasting multiple files, deleting multiple files and downloading multiple files. In another way, multiple files can be selected by mouse down and drag over the desired files. In addition to that, additional files can be selected with the preselected file by holding the ctrl/shift key and drag the mouse over the files. Also, holding the ctrl/shift key and dragging over selected files will unselect the selected files.

The [select](https://help.syncfusion.com/api/js/ejfileexplorer#events:select) event will be triggered when the items of FileExplorer control is selected.
Also [unselect](https://help.syncfusion.com/api/js/ejfileexplorer#events:unselect) event will be triggered when the items of FileExplorer control is unselected.

N>  For selecting files by mouse down and drag set `AllowMultiSelection` property as true.

In the view page, add FileExplorer element and specify the following settings to enable multi selection.
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            AllowMultiSelection="true" 
            ShowCheckbox="false">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
        <%--AllowMultiSelection property is true by default--%>
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
    
    
