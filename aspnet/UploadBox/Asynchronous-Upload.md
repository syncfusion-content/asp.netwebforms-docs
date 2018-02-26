---
layout: post
title: Asynchronous Upload | UploadBox | ASP.NET | Syncfusion
description: asynchronous upload
platform: aspnet
control: UploadBox
documentation: ug
---

# Asynchronous Upload

This feature allows you to upload and remove files asynchronously. When multiple files are chosen in Asynchronous upload,files will be uploaded one by one to the server.User interaction with the page will not be interrupted at the time of upload.User can also remove the file even after uploading.This is the best way of file upload when compared to synchronous so by default UploadBox works with asynchronous upload option only.To achieve this, set the AsyncUpload property to true. The default value of AsyncUpload property is true. The data type is Boolean.

The following steps guide you to upload the file asynchronously.

 In the ASPX page, add the UploadBox element and enable the AsyncUpload property.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" AsyncUpload="true" ></ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

