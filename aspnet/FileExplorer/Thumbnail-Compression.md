---
title: Thumbnail Image Compression | FileExplorer | ASP.NET Web | Syncfusion
description: Thumbnail image compression option in FileExplorer
platform: aspnet
control: FileExplorer
documentation: UG
keywords: Thumbnail image compression option
---

# Thumbnail Image Compression Support

The “FileExplorer” allows thumbnail images to be compressed on the server side and loaded into the “FileExplorer” layout to improve performance when working with large size images. You can enable this option using “**EnableThumbnailCompress**” API of FileExplorer. For enabling this API, [showThumbnail](https://help.syncfusion.com/api/js/ejfileexplorer#members:showthumbnail) must be set to true in order to render thumbnail preview of images in Tile and LargeIcons layout.

The [beforeGetImage](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforegetimage) event is triggered before loading a requested image from the server and [getImage](https://help.syncfusion.com/api/js/ejfileexplorer#events:getimage) event is triggered after the requested image is loaded.

Refer following code block that will be helpful to you.

In the aspx page, add “FileExplorer” element and specify the thumbnail image compress option as specified below.


    {% highlight html %}

        <ej:FileExplorer ID="fileexplorer1" 
            runat="server"
            Layout="Tile" 
            AjaxAction="FileExplorerFeatures.aspx/FileActionDefault"
            Path="~/content/images/FileExplorer/"  
            EnableThumbnailCompress="true">
            <AjaxSettings>
                <GetImage Url="getImage.ashx{0}" />
                <Download Url="downloadFile.ashx{0}" />
                <Upload Url="uploadFiles.ashx{0}" />
            </AjaxSettings>
        </ej:FileExplorer>

    {% endhighlight %}


Add an ashx handler file and specify the “**getImage**” handling operation as shown below. This handling function is necessary to compress and load the images in “FileExplorer”, while “EnableThumbnailCompress” option has been enabled.


    {% highlight c# %}
    
    using Syncfusion.JavaScript;
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Web;
    using System.Web.Script.Serialization;

    namespace WebSampleBrowser.FileExplorer
    {
        /// <summary>
        /// Summary description for getImage
        /// </summary>
        public class getImage : IHttpHandler
        {
            //Helps to reduce thumbnail image size before loading it into FileExplorer
            public void ProcessRequest(HttpContext context)
            {
                HttpRequest request = context.Request;
                string path = request.QueryString["Path"];
                var serializer = new JavaScriptSerializer();
                ImageSize imageSize = (ImageSize)serializer.Deserialize(request.QueryString["Size"], typeof(ImageSize));
                bool canCompress = (bool)serializer.Deserialize(request.QueryString["CanCompress"], typeof(bool));            
                new FileExplorerOperations().GetImage(path, canCompress, imageSize, null);
            }

            public bool IsReusable
            {
                get
                {
                    return false;
                }
            }
        }
    }

    {% endhighlight %}

