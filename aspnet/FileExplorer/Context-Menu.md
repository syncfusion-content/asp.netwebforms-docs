---
title: Context Menu | FileExplorer | ASP.NET Web | Syncfusion
description: Context Menu support in FileExplorer 
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Context Menu
---
# Context Menu

The context-menu has [list of items](#context-menu-items) which helps to perform FileExplorer operations, and it appears based on the target such as file or folder.

## Context menu items

The below table shows the context menu items corresponding to the location where it is opened:

<table>
<tr>
<td>
Context menu location
</td>
<td>
Context menu items
</td>
<td>
Screenshot
</td>
</tr>
<tr>
<td>
While right click on treeview nodes (from navigation pane)<br/><br/></td>
<td>
* New folder<br/>* Upload<br/>* Delete<br/>* Rename<br/>* Cut<br/>* Copy<br/>* Paste<br/>*Get info<br/><br/><br/></td>
<td>
<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
While right click on file / folder<br/><br/></td>
<td>
* Open<br/>* Download<br/>* Upload<br/>* Delete<br/>* Rename<br/>* Cut<br/>* Copy<br/>* Paste<br/>* Get info<br/>*Open folder location<br/><br/><br/><br/></td>
<td>
<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
While right click on layout (content pane)<br/><br/></td>
<td>
* Refresh<br/>* Paste<br/>* New folder<br/>* Upload <br/>* Get info <br/><br/><br/><br/></td>
<td>
<br/><br/><br/><br/></td>
</tr>
</table>
The below table explains the behavior of each context menu item:
<table>
<tr>
<td>
Open<br/><br/></td>
<td>
It opens the selected folder. When an image file selected it opens the preview of the image. For the remaining files this option becomes disabled.<br/><br/></td>
</tr>
<tr>
<td>
Download<br/><br/></td>
<td>
It downloads the selected file. When a file or number of files selected at that time only download option enabled.<br/><br/>If multiple files selected then it downloads all the files in a zip format.<br/><br/></td>
</tr>
<tr>
<td>
Cut<br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files in any location, the files are removed from the source location.<br/><br/></td>
</tr>
<tr>
<td>
Copy<br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files, the copy of the files only pasted in the target location.<br/><br/></td>
</tr>
<tr>
<td>
Paste<br/><br/></td>
<td>
It paste the files from the clipboard into the current selected folder. Note that when the files are copied into the clipboard at that time only it enabled.<br/><br/></td>
</tr>
<tr>
<td>
Delete<br/><br/></td>
<td>
It deletes the current selected file or folder. When you select any file or folder at that time only this option gets enabled.<br/><br/>If multiple files selected then it deletes all the selected items.<br/><br/></td>
</tr>
<tr>
<td>
Rename<br/><br/></td>
<td>
This is used to rename the current selected file or folder. When you select any file or folder at that time only this option gets enabled.<br/><br/>Even multiple files selected it renames the single file only.<br/><br/></td>
</tr>
<tr>
<td>
New Folder<br/><br/></td>
<td>
It creates a new folder on the current directory.<br/><br/>While click on the “New folder” item a dialog appears to get the folder name. Based on the user input, a new folder create on the current directory.<br/><br/></td>
</tr>
<tr>
<td>
Upload<br/><br/></td>
<td>
It uploads a file or list of files into the current directory.<br/><br/></td>
</tr>
<tr>
<td>
Get info<br/><br/></td>
<td>
It displays the details of the current selected file or folder.<br/><br/></td>
</tr>
<tr>
<td>
Open folder location
</td>
<td>
It helps to open a file location from the filtered list.
</td>
</tr>
</table>

## Context menu Visibility

The presence of the context menu can be controlled by the “[ShowContextMenu](http://help.syncfusion.com/js/api/ejfileexplorer#members:showcontextmenu)” property. This was enabled by default, and by disabling this property you can prevent our built-in context menu.

In the view page, add FileExplorer element and specify the context menu visibility as false.

    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            ShowContextMenu="false">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>  
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Enable / Disable the Context menu Item

The context menu items can be enabled or disabled through the client side public methods. It enables or disables the item from all the context menu where it is present.

For example, if you disable the “Upload” item, it disables in all places wherever it appears such as open navigation pane, open on file/ folder, and open on layout.

* [enableMenuItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:enablemenuitem)
* [disableMenuItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:disablemenuitem)

These methods only accepts the context menu item name as the parameter.
    
    {% highlight javascript %}
    
            $(function () {
                var fileExpObj = $("#fileexplorer").data("ejFileExplorer");
                // this disables the New folder item
                fileExpObj.disableMenuItem("New folder");
                // this disables the Download item
                fileExpObj.disableMenuItem("Download");
            });
            
    {% endhighlight %}
    
