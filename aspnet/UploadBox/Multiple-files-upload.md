---
layout: post
title: Multiple-files-upload
description: multiple files upload
platform: aspnet
control: UploadBox
documentation: ug
---

## Multiple files upload

The UploadBox control provides support to upload multiple files spontaneously. The MultipleFilesSelection property enables you to select multiple files while browsing.  To achieve this, set the MultipleFilesSelection property to true. The data type is Boolean.

_Note: The Multiple file selection supports all the latest versions of browser except Internet Explorer 9 and its previous versions__._



The following steps explain the configuration of the MultipleFilesSelection property in the UploadBox. 

In the ASPX page, add the UploadBox element.



{% highlight html %}



<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" MultipleFilesSelection="true" > </ej:UploadBox>





{% endhighlight %}

> _Note: The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section)._

The following screenshot displays the output.



{ ![](Multiple-files-upload_images/Multiple-files-upload_img1.png) | markdownify }
{:.image }




{ ![](Multiple-files-upload_images/Multiple-files-upload_img2.png) | markdownify }
{:.image }


