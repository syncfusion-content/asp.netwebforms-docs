---
title: Resizing | FileExplorer | ASP.NET Web | Syncfusion
description: Resize option in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: FileExplorer,  Syncfusion, ASP.NET Web FileExplorer, UG document, Resizing
---
# Resizing

The FileExplorer has the resize support through the resize handle which appears at right-bottom corner of footer. By clicking the resize handle the user can resize the FileExplorer through the UI. While resizing the dimension of the FileExplorer is automatically adjusted.

The resize behavior can be enabled through the “[EnableResize](http://help.syncfusion.com/js/api/ejfileexplorer#members:enableresize)” property.

In the view page, add FileExplorer element with resizable option as shown below.
    
    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            EnableResize="true">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Responsiveness

By enabling the “[IsResponsive](http://help.syncfusion.com/js/api/ejfileexplorer#members:isresponsive)” property, you can make the FileExplorer as responsive. While resizing the FileExplorer component, the inner content and toolbar items are automatically adjusted to equalize the size. The toolbar items are displayed within Dropdown on enabling the responsive. Otherwise it floated to the next line to equalize the space.

In the view page, add FileExplorer element with responsive option.
    
    {% highlight html %}
    
        <%--It enables the resize functionality by adding resize handler at footer and enables the responsiveness of this control--%>
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            EnableResize="true" 
            IsResponsive="true">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
        
    {% endhighlight %}
    
## Restriction on Resize

You can restrict the dimension of the FileExplorer by setting the “[MinHeight](http://help.syncfusion.com/js/api/ejfileexplorer#members:minheight)”, “[MaxHeight](http://help.syncfusion.com/js/api/ejfileexplorer#members:maxheight)”,  “[MinWidth](http://help.syncfusion.com/js/api/ejfileexplorer#members:minwidth)” and “[MaxWidth](http://help.syncfusion.com/js/api/ejfileexplorer#members:maxwidth)” properties while resizing the FileExplorer.

In the view page, add FileExplorer element and set resize option within particular region.

    {% highlight html %}
    
        <ej:FileExplorer
            ID="fileexplorer"
            runat="server"
            AjaxAction="DefaultFunctionalities.aspx/FileActionDefault"
            Path="~/FileBrowser/" 
            EnableResize="true" 
            IsResponsive="true" 
            MinHeight="200px" 
            MaxHeight="400px" 
            MinWidth="300px" 
            MaxWidth="1200px">        
            <AjaxSettings>
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>       
        </ej:FileExplorer>
        
    {% endhighlight %}

