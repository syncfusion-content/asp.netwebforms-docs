---
layout: post
title: Uploading Restriction | UploadBox | ASP.NET | Syncfusion
description: restricting uploading files based on its extension
platform: aspnet
control: UploadBox
documentation: ug
---

# Restricting uploading files based on its extension

## Allow Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using the Browse button. 
The ExtensionAllow property allows upload of the selected extensions only. You can give multiple extensions by using comma (,).  The data type is string.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following steps explain the configuration of the ExtensionAllow property in the UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="UploadBox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" ExtensionsAllow=".docx,.pdf" MultipleFilesSelection="true"> 

</ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

The following screenshot displays the output when multiple files of different file types are selected and only the allowed file extensions are uploaded.

![Allow Extension](Restricting-uploading-files-based-on-its-extension_images/Restricting-uploading-files-based-on-its-extension_img1.png)



## Deny Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using the Browse button. The ExtensionDeny property denies upload of the selected extensions. You can give multiple extensions by using comma (,).  The data type is string.

N> Prepend dot (.) symbol with extension like “.pdf”.


The following steps explain the configuration of the ExtensionDeny property in the UploadBox

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="UploadBox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" ExtensionsDeny=".docx,.pdf" MultipleFilesSelection="true">

</ej:UploadBox>


{% endhighlight %}


N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

The following screenshot displays the output when multiple files of different file types are selected and the denied file extensions are not uploaded.

![Deny Extension](Restricting-uploading-files-based-on-its-extension_images/Restricting-uploading-files-based-on-its-extension_img2.png)

N> When **ExtensionsDeny** and **ExtensionsAllow** properties have same file extension, the extension will be allowed.