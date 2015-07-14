---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: UploadBox
documentation: ug
---

# Getting Started

## Create your first UploadBox in ASP.NET

ASP.NET WebForms UploadBox provides support to upload the files or photos within your webpage. From the following guidelines, you can learn how to upload the file by using Resume Upload scenario. This helps you to restrict some file extensions while uploading the resume in the server by using UploadBox control. The following screenshot demonstrates the functionality of UploadBox with file extension.

{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


In the above screenshot, you can upload a resume with .png and .docx file extensions. This stops unsupported resume formats from being uploaded to the server.

Create UploadBox widgets

ASP.NET UploadBox widget has built-in features like Upload multiple files, Delete files, check the status of the file, whether it shows complete or failed, and retry uploading the files.  You can easily create the UploadBox by using the following steps.

You can create a Web project and add the necessary assemblies, styles, and scripts with the help of the given [ASP-Getting Started](http://help.syncfusion.com/ug/js/Documents/gettingstartedwithmv.htm) Documentation.{ ![](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }
 Add the following code example to the ASPX page to render the UploadBox.





&lt;div class="posupload"&gt;

<b>Select a file to upload</b>

&lt;br /&gt;&lt;br /&gt;

&lt;ej:UploadBox ID="Upload1" runat="server" SaveUrl="saveFiles.ashx" RemoveUrl="removeFiles.ashx" AutoUpload="false"&gt;&lt;/ej:UploadBox&gt;

&lt;/div&gt;



Add the given styles to show the UploadBox with margin alignments.

        .posupload

        {

            margin-left: 20px;

            margin-top: 20px;

        }        

        .control

        {

            margin-left: 15px;

        }



Add the handlers to save and remove the files uploaded by using the UploadBox. Create a new handler file .ashx and save as saveFile.ashx and add the following code to it. 

public void ProcessRequest(HttpContext context)

    {

        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

        if (!Directory.Exists(targetFolder))

        {

            Directory.CreateDirectory(targetFolder);

        }

        HttpRequest request = context.Request;

        HttpFileCollection uploadedFiles = context.Request.Files;

        if (uploadedFiles != null && uploadedFiles.Count > 0)

        {

            for (int i = 0; i < uploadedFiles.Count; i++)

            {

                if (uploadedFiles[i].FileName != null && uploadedFiles[i].FileName != "")

                {

                    string fileName = uploadedFiles[i].FileName;

                    int indx = fileName.LastIndexOf("\\");

                    if (indx > -1)

                    {

                        fileName = fileName.Substring(indx + 1);

                    }

                    uploadedFiles[i].SaveAs(targetFolder + "\\" + fileName);

                }

            }

        }



    }    





Create a new handler file .ashx and save as removeFile.ashx and add the following code to it. 

public void ProcessRequest(HttpContext context)

    {

        System.Collections.Specialized.NameValueCollection s = context.Request.Params;

        string fileName = s["fileNames"];

        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

        if (Directory.Exists(targetFolder))

        {

            string physicalPath = targetFolder + "\\" + fileName;

            if (System.IO.File.Exists(physicalPath))

            {

                System.IO.File.Delete(physicalPath);

            }

        }     



    }



Run the code to render the following output.

{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


Run the project to see the following output for the given steps. The file is uploaded. 

{ ![](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }


Set Restrictions to File Extensions

In a real-time scenario, some file extensions are restricted. You can allow files or restrict files by using the following properties, fileallow and filedeny enabled in the UploadBox. 

> _Note: The SaveUrl and RemoveUrl are the same as above._

Add the following code example to the script section.

        var uploadobject;

        function allowfiletype() {

            uploadobject = $("#&lt;%=Upload1.ClientID%&gt;").data("ejUploadbox");

            uploadobject.option('extensionsAllow', $("#fileallow").val());

            uploadobject.option('extensionsDeny', "");

            $("#filedeny").val('');

        }

        function denyfiletype() {

            uploadobject = $("#&lt;%=Upload1.ClientID%&gt;").data("ejUploadbox");

            uploadobject.option('extensionsAllow', "");

            uploadobject.option('extensionsDeny', $("#filedeny").val());

            $("#fileallow").val('');

        }



Add input elements to create elements for file extensions.

_Note: Add the following input elements and two button elements to give file extensions that should support uploading._



    &lt;div class="posupload"&gt;

        <b>Select a file to upload</b>

        &lt;br /&gt;

        &lt;br /&gt;

        <ej:UploadBox ID="Upload1" SaveUrl="saveFiles.ashx" RemoveUrl="removeFiles.ashx"

            ExtensionsAllow=".docx" ExtensionsDeny=".pdf" runat="server">

        &lt;/ej:UploadBox&gt;

        &lt;label id="extdetails"&gt;

            By default, it allow .docx format and deny .pdf format files

        &lt;/label&gt;

    &lt;/div&gt;

    &lt;br /&gt;

    &lt;br /&gt;

    &lt;div style="margin-left: 15px"&gt;

        <b>Setting Restriction</b>&lt;/div&gt;

    &lt;div class="allow_deny"&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-3"&gt;

                Extensions:

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-3"&gt;

                &lt;input type="text" id="fileallow" class="tb6 ejinputtext" /&gt;

            &lt;/div&gt;

            &lt;div class="col-md-3"&gt;

                <ej:Button ID="upbutton1" Type="Button" CssClass="e-btn" Text="Allow" ClientSideOnClick="allowfiletype"

                    runat="server">

                &lt;/ej:Button&gt;

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-3"&gt;

                &lt;input type="text" id="filedeny" class="tb6 ejinputtext" /&gt;

            &lt;/div&gt;

            &lt;div class="col-md-3"&gt;

                <ej:Button ID="upbutton2" Type="Button" CssClass="e-btn" Text="Deny" ClientSideOnClick="denyfiletype"

                    runat="server">

                &lt;/ej:Button&gt;

            &lt;/div&gt;

        &lt;/div&gt;

    &lt;/div&gt;





1. Add the following Styles in the ASPX page to allow or deny files.

        .posupload

        {

            margin-left: 20px;

            margin-top: 20px;

        }



        .control

        {

            margin-left: 15px;

        }



        .ctrl

        {

            border: 1px solid #ccc;

            border-radius: 10px;

            width: 150px;

            padding: 50px 100px 50px 100px;

            float: left;

        }



        .allow_deny

        {

            border: 1px solid #ccc;

            border-radius: 10px;

            float: left;

            margin: 10px;

            padding: 15px;

        }





Run the code to render the following output with the file extensions.

> _Note: You can restrict one or more files at a time by giving it as .html,.txt._

In the UploadBox control, you can either allow files with specified extension only by using the ExtensionAllow property or deny files with specified extension only by using the ExtensionDeny property.

The following screenshot displays an UploadBox control with the file extension.

{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }


Upload Multiple Files

To upload multiple files in the UploadBox control, click the Browse button to select files. The selected files appear in the UploadBox control and you can upload those files.

The following screenshot displays an UploadBox control with multiple files selected.

{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }


