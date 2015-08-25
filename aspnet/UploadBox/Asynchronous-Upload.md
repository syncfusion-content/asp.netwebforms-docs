---
layout: post
title: Asynchronous-Upload
description: asynchronous upload
platform: aspnet
control: UploadBox
documentation: ug
---

# Asynchronous Upload

This feature allows you to upload and remove files asynchronously. To achieve this, set the AsyncUpload property to true. The default value of AsyncUpload property is true. The data type is Boolean.

The following steps guide you to upload the file asynchronously.

 In the ASPX page, add the UploadBox element and enable the AsyncUpload property.

{% highlight html %}



    <ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" AsyncUpload="true" ></ej:UploadBox>





{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

