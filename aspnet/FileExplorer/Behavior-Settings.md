---
title: Behavior Settings | FileExplorer | ASP.NET Web | Syncfusion
description: Customize the behavior of FileExplorer.
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion,  ASP.NET Web FileExplorer, UG document, Behavior settings
---
# Behavior Settings

Here are the some properties to customize the behavior of FileExplorer.

## File type restriction

FileExplorer control showcase all the files from the filesystem, here you can customize the file types that what you want to show by using “[FileTypes](http://help.syncfusion.com/js/api/ejfileexplorer#members:filetypes)” property. It filter the files based on the file extensions.

By default it having the value “\*.\*”, so it allows all the file types. In case of image browser you can allow the image files only by setting “*.png, *.gif, *.jpg, *.jpeg”, so it doesn’t allow the other type of files.

In the view page, add FileExplorer element and specify the file type restriction as shown below.

    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            Layout="Tile"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/"
            FileTypes="*.png, *.gif, *.jpg, *.jpeg, *.docx">
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Customize the AJAX request settings

As you already know FileExplorer is a client – server based control and each action performed in the client sends an AJAX request to the server to perform the server side operations. While the AJAX request, the AJAX configurations can be customized through “[AjaxSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:ajaxsettings)” property.

The [beforeAjaxRequest](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeajaxrequest) event will be triggered before the AJAX request is performed. You can modify the ajax request in this event.

You can see the following requests passed during the **client – server** actions:

* Read
* Create folder
* Remove
* Rename
* Paste
* Get details
* Upload
* Download
* Get Image
* Search

The actions “Read, CreateFolder, Remove, Rename, Paste, GetDetails, Search” are supported all the jQuery AJAX configurations. The remaining actions “Upload, Download, GetImage” are accepted the URL only.

If you want to customize read action alone, the Ajax “**Url”** and “**DataType”** are changed for the “Read” action.

In the view page, add FileExplorer element and specify the AJAX settings for Read request as shown below.
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            Layout="Tile"
            AjaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"
            Path="http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/">
            <AjaxSettings>
                <Read Url="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperationsCors" DataType="jsonp" />
            </AjaxSettings>
        </ej:FileExplorer>
        
    {% endhighlight %}
    
