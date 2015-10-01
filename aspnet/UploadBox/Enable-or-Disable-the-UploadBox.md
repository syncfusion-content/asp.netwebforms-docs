---
layout: post
title: Enable or Disable the UploadBox | UploadBox | ASP.NET | Syncfusion
description: enable or disable the uploadbox 
platform: aspnet
control: UploadBox
documentation: ug
---

# Enable or Disable the UploadBox 

This features helps to set the Enable or Disable option for UploadBox by setting the Boolean type value to Enabled property. For Enable or Disable option, set the Enabled property to false. The data type is Boolean.

The following steps explain the configuration of the Enabled property in UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" Enabled="false" ></ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

The following screenshot displays the output for Disabled UploadBox.

![](Enable-or-Disable-the-UploadBox_images/Enable-or-Disable-the-UploadBox_img1.png)