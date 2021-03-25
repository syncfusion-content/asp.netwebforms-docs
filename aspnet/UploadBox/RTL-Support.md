---
layout: post
title: RTL Support | UploadBox | ASP.NET | Syncfusion
description: Learn about RTL support in Syncfusion ASP.NET Webforms UploadBox control and more details. 
platform: aspnet
control: UploadBox
documentation: ug
---

# RTL Support 

This feature supports the change of left-to-right alignment of the UploadBox control to right-to-left (RTL). That is, it sets the UploadBox to right-to-left actions.

The following steps explain the configuration of the EnableRTL property in the UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" EnableRTL="true"></ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

The following screenshot displays the output for RTL support.

 ![ASPNET UploadBox RTL-Support Image1](RTL-Support_images/RTL-Support_img1.png)



