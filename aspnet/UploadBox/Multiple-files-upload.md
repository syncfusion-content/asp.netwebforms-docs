---
layout: post
title: Multiple Files Upload in ASP.NET Web Forms UploadBox | Syncfusion
description: Learn here all about multiple files upload support in Syncfusion ASP.NET Web Forms UploadBox control, it's elements and more.
platform: aspnet
control: UploadBox
documentation: ug
---

# Multiple Files Upload in ASP.NET Web Forms UploadBox

The UploadBox control provides support to upload multiple files spontaneously. The MultipleFilesSelection property enables you to select multiple files while browsing.  To achieve this, set the MultipleFilesSelection property to true. The data type is Boolean.

N> The Multiple file selection supports all the latest versions of browser except Internet Explorer 9 and its previous versions.


The following steps explain the configuration of the MultipleFilesSelection property in the UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" MultipleFilesSelection="true" > </ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

The following screenshot displays the output.

![Multiple files upload in ASP.NET Web Forms UploadBox.](multiple-files-upload_images/aspnet-web-forms-uploadbox-multiple-files-upload.png)

![File upload in ASP.NET Web Forms UploadBox.](multiple-files-upload_images/aspnet-web-forms-uploadbox-files-upload.png)