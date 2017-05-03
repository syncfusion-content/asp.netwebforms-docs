---
layout: post
title: File Actions | UploadBox | ASP.NET | Syncfusion
description: file actions
platform: aspnet
control: UploadBox
documentation: ug
---

# File Actions

## Save File Action 

To save the uploaded file, create the handlers class and trigger the same in the SaveUrl property.  In those handlers, save and specify the target location for the uploaded files. Its data type is string type.

The following steps explain the configuration of the SaveUrl property in the UploadBox

In the ASPX page, add the UploadBox element.


{% highlight html %}
<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" > </ej:UploadBox>
{% endhighlight %}


Configure the handler to save the file as SaveFiles.ashx. Create a folder (for example, uploadfiles) and save the uploaded files into this folder.  

{% highlight c# %}
public class SaveFiles : IHttpHandler

{

    public void ProcessRequest(HttpContext context)

    {

        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

        if (!System.IO.Directory.Exists(targetFolder))

        {

            System.IO.Directory.CreateDirectory(targetFolder);

        }

        HttpRequest request = context.Request;

        HttpFileCollection uploadedFiles = context.Request.Files;

        if (uploadedFiles != null && uploadedFiles.Count > 0)

        {

            for (int i = 0; i < uploadedFiles.Count; i++)

            {

                string fileName = uploadedFiles[i].FileName;

                int index = fileName.LastIndexOf("\\");

                if (index > -1)

                {

                    fileName = fileName.Substring(index + 1);

                }

                uploadedFiles[i].SaveAs(targetFolder + "\\" + fileName);

            }

        }

    }

    public bool IsReusable

    {

        get

        {

            return false;

        }



    }

}

{% endhighlight %}

The following screenshot displays the output. 

 ![](File-Actions_images/File-Actions_img1.png)



## Remove File Action 

To remove the uploaded file, create the handlers class and trigger the same in the RemoveUrl property.  In the handlers, remove the file where you have saved the uploaded file. This can be achieved by clicking the remove button on upload dialog. Its data type is string type.

The following steps explains the configuration of the RemoveUrl property in the UploadBox

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx"> </ej:UploadBox>  

{% endhighlight %}

Configure the handlers to remove the file from the target location named, RemoveFiles.ashx. From that location, the file is searched and removed from the uploadfiles folder.

{% highlight c# %}
public class RemoveFiles : IHttpHandler

{

    public void ProcessRequest(HttpContext context)

    {

        System.Collections.Specialized.NameValueCollection s = context.Request.Params;

        string fileName = s["fileNames"];

        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");

        if (!System.IO.Directory.Exists(targetFolder))

        {

            System.IO.Directory.CreateDirectory(targetFolder);

        }



        string physicalPath = targetFolder + "\\" + fileName;

        if (System.IO.File.Exists(physicalPath))

        {

            System.IO.File.Delete(physicalPath);

        }

    }


    public bool IsReusable
    {

        get
        {

            return false;

        }

    }

}

{% endhighlight %}



The following screenshot displays the output. 

 ![](File-Actions_images/File-Actions_img2.png)



