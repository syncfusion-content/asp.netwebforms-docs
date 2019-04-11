---
title: Toolbar | FileExplorer | ASP.NET Web | Syncfusion
description: Toolbar support in FileExplorer control
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Toolbar
---
# Toolbar

The toolbar element having the number of tools, and each tool can be configurable.

## Toolbar items

The toolbar having the list of items to perform various operations and grouped into some categorizes.

From below you can see the available toolbar items and its categorization:

    
    {% highlight c# %}
    
            protected void Page_Load(object sender, EventArgs e)
            {
                //all tools categories are placed in the toolbar by the below order
                this.fileexplorer.ToolsList = new List<string>() { 
                    "creation",
                    "navigation",
                    "addressBar",                
                    "copyPaste",                
                    "searchBar",
                     "sortBy"               
                };
    
                //all tools grouped under following categories
                this.fileexplorer.Tools.Creation = new List<string>(){
                    "NewFolder"
                };
                this.fileexplorer.Tools.Navigation = new List<string>() {
                    "Back",
                    "Forward",
                    "Upward"
                };
                this.fileexplorer.Tools.AddressBar = new List<string>() {
                    "Addressbar"
                };
                this.fileexplorer.Tools.CopyPaste = new List<string>() {
                    "Cut",
                    "Copy",
                    "Paste"
                };
                this.fileexplorer.Tools.SearchBar = new List<string>() {
                    "Searchbar"
                };
                this.fileexplorer.Tools.SortBy = new List<string>() {
                    "SortBy"
                };
            }
    
    {% endhighlight %}
    
The following table explains the functionality of each toolbar item:

<table>
<tr>
<td>
Tool name
</td>
<td>
Description
</td>
</tr>
<tr>
<td>
Layout
</td>
<td>
In FileExplorer, files have been displayed in 3 types of views “Grid”, “Tile” and “Large Icons”. Using this tool, you can change the view type from one to another.

</td>
</tr>
<tr>
<td>
NewFolder <br/><br/></td>
<td>
It creates a new folder on the current directory.<br/><br/>While click on the NewFolder item, the dialog displays to get the folder name. Based on the user input, FileExplorer creates new folder on the current directory.
Also {{'[createFolder](https://help.syncfusion.com/api/js/ejfileexplorer#events:createfolder)'| markdownify}} event will be triggered when new folder is created successfully in the file system.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Back <br/><br/></td>
<td>
It navigates to the previous directory from the user history. When the backward history is not available when it is disabled state.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Forward <br/><br/></td>
<td>
It navigates to the next directory from the user history. When the forward history is not available when it is disable state.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Upward <br/><br/></td>
<td>
It navigates to the parent directory of the current folder.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Address bar<br/><br/></td>
<td>
The “address bar” is the textbox which displays the path of the current directory, as a series of its parent directory separated by slash (“/”).<br/><br/>And the address bar is an editable area, so you can enter any directory’s path to a quick navigation.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Refresh <br/><br/></td>
<td>
It refreshes the current directory.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Upload <br/><br/></td>
<td>
It uploads a file or list of files into the current directory.<br/><br/>And you can customize the upload configurations, for details check {{'[here](https://help.syncfusion.com/js/fileexplorer/toolbar#customizing-the-upload-functionality)'| markdownify }}.
<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Delete <br/><br/></td>
<td>
It delete the current selected file or folder. The delete icon is enable state if you select any file or folder.<br/><br/>If you selected the multiple files, it deletes all the selected items.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Rename <br/><br/></td>
<td>
This is used to rename the current selected file or folder. The rename icon is enable state if you select any file or folder.<br/><br/>Even if you selected multiple files, it renames the last selected file only.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Download <br/><br/></td>
<td>
It downloads the selected files. The download icon is enable state if you select any file or folder.<br/><br/>
The {{'[beforeDownload](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforedownload)'| markdownify}} event will be triggered before the files are downloaded.
<br/><br/>If you select multiple files, it downloads all the files in a zip format.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Cut <br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files in any location, the files are removed from the source location.
The {{'[cut](https://help.syncfusion.com/api/js/ejfileexplorer#events:cut)'| markdownify}} event will be triggered when files or folders are removed from the source.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Copy <br/><br/></td>
<td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files, the copy of the files are pasted in the target location.
The {{'[copy](https://help.syncfusion.com/api/js/ejfileexplorer#events:copy)'| markdownify}} event will be triggered when file or folder is copied.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Paste <br/><br/></td>
<td>
It pastes the files from the clipboard into the currently selected folder. <br/><br/>Note: Only when the files are copied into the clipboard it is enabled.
The {{'[paste](https://help.syncfusion.com/api/js/ejfileexplorer#events:paste)'| markdownify}} event will be triggered when file or folder is pasted.<br/><br/><br/><br/></td></tr>
</tr>
<tr>
<td>
Details <br/><br/></td>
<td>
It displays the details of the current selected file or folder.<br/><br/><br/><br/></td>
</tr>
<tr>
<td>
Search bar<br/><br/></td>
<td>
The Search bar is the textbox which is used to search the files from the current directory. It list the files based on the user search.<br/><br/>The search behavior of the “search bar” can be customize, for details check <br/>{{'[here](#search-bar)'| markdownify }}.<br/><br/></td>
</tr>
<tr>
<td>
Sort by <br/><br/></td><td>
It's used to sorting the files from the current directory.The sorting can be done based on the columns available from grid,in both ascending and descending order.<br/><br/><br/><br/></td>
</tr>
</table>

## Toolbar Visibility

The visibility of the toolbar can be customized through the “[ShowToolbar](http://help.syncfusion.com/js/api/ejfileexplorer#members:showtoolbar)” property. By disabling this property you can remove the toolbar from FileExplorer. Also you can remove the particular toolbar item by using [removeToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:removetoolbaritem) method.

In the view page, add FileExplorer element and specify “**ShowToolbar**” as “**false**”
    
    {% highlight html %}
    
        <%--hides the toolbar--%>
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/"
            ShowToolbar="false">
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>
    
    {% endhighlight %}
    
## Toolbar Configuration

As you can see the available toolbar items from [here](#toolbar-items). From the list of available items, you can configure and group your required toolbar items only through the “[Tools](http://help.syncfusion.com/js/api/ejfileexplorer#members:tools)” property. And also you can arrange the toolbar items by the “[ToolsList](http://help.syncfusion.com/js/api/ejfileexplorer#members:toolslist)” property.

Add the following code example to the corresponding code behind page to create the tools list.
    
    
    {% highlight c# %}
    
            protected void Page_Load(object sender, EventArgs e)
            {
                this.fileexplorer.ToolsList = new List<string>() { 
                    "creation",
                    "navigation",
                    "addressBar",                
                    "copyPaste",                
                    "searchBar"                
                };
                this.fileexplorer.Tools.Creation = new List<string>(){
                    "NewFolder"
                };
                this.fileexplorer.Tools.Navigation = new List<string>() {
                    "Back",
                    "Forward",
                    "Upward"
                };
                this.fileexplorer.Tools.AddressBar = new List<string>() {
                    "Addressbar"
                };
                this.fileexplorer.Tools.CopyPaste = new List<string>() {
                    "Cut",
                    "Copy",
                    "Paste"
                };
                this.fileexplorer.Tools.SearchBar = new List<string>() {
                    "Searchbar"
                };
            }
    
    {% endhighlight %}
    
In the view page, add FileExplorer element as shown below
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/">
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>
    
    {% endhighlight %}
    
## Search bar

The Search bar can be customize through the “[FilterSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:filtersettings)” property. By default the search doesn’t consider the case sensitivity, and the search works based on “[FilterType](http://help.syncfusion.com/js/api/ejfileexplorer#members:filtersettings-filtertype)”.

The FileExplorer allows the following filter types in the search functionality.

* “FilterOperator.StartsWith” – Supports to search text with starts with

* “FilterOperator.Contains” – Supports to search text with contains with

* “FilterOperator.EndsWith” – Supports to search text with ends with

In the view page, you can configure the filter type with enabling case sensitivity like below:

    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/">
            <%--it changes the search filter type as “startsWith” and enables the case sensitive search--%>
            <FilterSettings FilterType="StartsWith" CaseSensitiveSearch="true" />
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Custom Tool in Toolbar

From the [toolbar items ](#toolbar-items)you can see the list of built-in tools to perform the operations. Along with this built-in tools, you can add your custom tool with the custom functionality.

You can find an online demo sample of FileExplorer with custom tool from [here](http://mvc.syncfusion.com/demos/web/fileexplorer/customtool#). 

Add the following code example to the corresponding code behind page to create a custom tools list.

    
    {% highlight c# %}
    
            protected void Page_Load(object sender, EventArgs e)
            {
                this.fileexplorer.ToolsList = new List<string>() {
                    "creation",
                    "navigation",
                    "addressBar",                
                    "copyPaste",                
                    "searchBar",
                    "customTool"
                };
                this.fileexplorer.Tools.Creation = new List<string>(){
                    "NewFolder"
                };
                this.fileexplorer.Tools.Navigation = new List<string>() {
                    "Back",
                    "Forward",
                    "Upward"
                };
                this.fileexplorer.Tools.AddressBar = new List<string>() {
                    "Addressbar"
                };
                this.fileexplorer.Tools.CopyPaste = new List<string>() {
                    "Cut",
                    "Copy",
                    "Paste"
                };
                this.fileexplorer.Tools.SearchBar = new List<string>() {
                    "Searchbar"
                };
            }
            
    {% endhighlight %}
    
In the view page, add FileExplorer element and specify custom tool as shown below
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
            <Tools>
                <CustomTool>
                    <ej:FileExplorerCustomTool 
                        Name="Help" 
                        Tooltip="Help" 
                        Action="dialogOpen" 
                        Css="e-fileExplorer-toolbar-icon Help" 
                    />
                </CustomTool>
            </Tools>
        </ej:FileExplorer>
        <script type="text/javascript">
            //click handler of custom tool
            function dialogOpen() {
                alert("custom tool item clicked");
            }
        </script>
        <style type="text/css">
            /*Specify the custom tool icon*/
            .e-fileExplorer-toolbar-icon {
                height: 22px;
                width: 22px;
                font-family: 'ej-webfont';
                font-size: 18px;
                margin-top: 2px;
                text-align: center;
            }
            .e-fileExplorer-toolbar-icon.Help:before {
                content: "\e72b";
            }
        </style>
        
    {% endhighlight %}
    
## Enable / Disable the Toolbar Item

Each toolbar item can be enabled or disabled through the below client-side public methods.

* [enableToolbarItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:enabletoolbaritem)
* [disableToolbarItem](http://help.syncfusion.com/js/api/ejfileexplorer#methods:disabletoolbaritem)

These methods accepts the tool name as the parameter. It also allows the parameter as tool item index or the jQuery object of the tool item.
    
    {% highlight javascript %}
    
            $(function () {
                var fileExpObj = $("#fileexplorer").data("ejFileExplorer");
                // this disables the NewFolder item
                fileExpObj.disableToolbarItem("NewFolder");
                // this disables the Layout item (since index of Layout is 0)
                fileExpObj.disableToolbarItem(0);
                // this enables the NewFolder item
                fileExpObj.enableToolbarItem("NewFolder");
            });
    
    {% endhighlight %}

### Enable / Disable the custom added tool in Toolbar Item

If you want to enable / disable the custom added tool in toolbar, you need to pass the corresponding li elements of custom added tool in [enableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:enabletoolbaritem) / [disableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:disabletoolbaritem) method of FileExplorer. Since we have consider this custom tool as a object type.

{% highlight javascript %}
        
        var fileExpObj = $("#fileExplorer").data("ejFileExplorer");
        
        //tool is a cssClass of FileExplorer 
        // this disables the custom tool item 
        
        var li = $(".tool").find(".Help").closest('li'); 
        fileExpObj.disableToolbarItem(li); 
        
        // this enables the custom tool item 
        fileExpObj.enableToolbarItem(li);

{% endhighlight %}

## Customizing the Upload Functionality

FileExplorer helps you to upload the file using [Upload](http://help.syncfusion.com/js/uploadbox/overview#) component. File upload can be done through the toolbar item or context menu item. The “[UploadSettings](http://help.syncfusion.com/js/api/ejfileexplorer#members:uploadsettings)” property is used to configure the upload functionalities.

This property has the below sub properties with the default values:
    
    {% highlight html %}
    
            <UploadBoxSettings 
                AllowMultipleFile="false" 
                AutoUpload="true" 
                MaxFileSize="31457280"             
            />
            
    {% endhighlight %}
    
**AllowMultipleFile**: This property used to control the behavior of multiple files upload and this was enabled by default so you can upload multiple files at a time. If you disable this “AllowMultipleFile” property then you can upload only one file at a time.

**MaxFileSize**: The property limits the maximum file size to upload. It accepts the value in bytes.

**AutoUpload**: when you enable this property, the upload action performed automatically after select the files. When you disable this property, it shows a confirmation dialog with the selected file details and perform the upload action on press the “upload” button.

If you want to upload more than 4 MB files in FileExplorer, you should specify the [maxRequestLength](https://msdn.microsoft.com/en-us/library/system.web.configuration.httpruntimesection.maxrequestlength.aspx) and [maxAllowedContentLength](https://msdn.microsoft.com/en-us/library/ms689462(v=vs.90).aspx) attribute in webconfig file. Please check the below code block.

{% highlight razor %}

<httpRuntime maxRequestLength="2147483647" /> 
     
<system.webServer> 
    <security> 
      <requestFiltering> 
        <requestLimits maxAllowedContentLength="3221225472" /> 
      </requestFiltering> 
    </security> 
… 
</system.webServer> 

{% endhighlight %}

Please find [Sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/uploadsettings-2078164286) for your reference.

N> maxRequestLength is measured in kilobytes and maxAllowedContentLength is measured in bytes.

During upload process following events will be triggered, {{'[beforeUploadSend](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeuploadsend)'| markdownify}}, {{'[beforeUploadDialogOpen](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeuploaddialogopen)'| markdownify}}, {{'[beforeUpload](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeupload)'| markdownify}}, {{'[uploadError](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploaderror)'| markdownify}}, {{'[uploadSuccess](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploadsuccess)'| markdownify}} and {{'[uploadComplete](https://help.syncfusion.com/api/js/ejfileexplorer#events:uploadcomplete)'| markdownify}}. You can customize the upload settings with these events

In the view page, add FileExplorer element and specify the upload settings as shown below

    
    {% highlight html %}
    
        <%--It disables the multi file upload functionality and enables the auto upload functionality--%>
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
            <UploadBoxSettings 
                AllowMultipleFile="false" 
                AutoUpload="true"
            />        
        </ej:FileExplorer>
        
    {% endhighlight %}
    
