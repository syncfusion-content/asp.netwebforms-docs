---
title: Drag and Drop Support | FileExplorer | ASP.NET Web | Syncfusion
description: Drag and Drop option in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: Drag and drop option
---

# Drag and Drop Support

The FileExplorer allows files to be moved from one folder to another by using drag and drop. It also supports uploading a file by dragging it from Windows Explorer to a folder in the FileExplorer control. You can enable or disable this support by using “**AllowDragAndDrop**” API of FileExplorer.

The [dragStart](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstart), [drag](https://help.syncfusion.com/api/js/ejfileexplorer#events:drag), [dragStop](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstop) and [drop](https://help.syncfusion.com/api/js/ejfileexplorer#events:drop) events occur in the mentioned order when a drag and drop operation is performed.

In the aspx page, add “FileExplorer” element and specify the drag and drop option as specified below.


    {% highlight html %}

        <ej:FileExplorer ID="fileexplorer1" 
            runat="server"
            IsResponsive="true"
            Width="100%"
            Layout="Tile" 
            AjaxAction="FileExplorerFeatures.aspx/FileActionDefault"
            Path="~/content/images/FileExplorer/" 
            AllowDragAndDrop="false" >
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>

    {% endhighlight %}

