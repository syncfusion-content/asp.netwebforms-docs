---
layout: post
title: RTL | Toolbar | ASP.NET | Syncfusion
description: rtl
platform: aspnet
control: Toolbar
documentation: ug
---

# RTL

This feature supports to change the left-to-right alignment of the Toolbar to right-to-left (RTL). That is, set the Toolbar to do their actions from right to left. The property EnableRTL sets the Toolbar from right to left. The value set to this property is a Boolean type. 

Add the following code example to the corresponding ASPX page to render the ToolBar Control



{% highlight html %}

<%--Refer Local Data section for style and data bound for toolbar items.--%>

<ej:Toolbar ID="toolbarcontent" runat="server" Height="100px" DataIdField="Id" DataTooltipTextField="Tooltip" DataSpriteCssClassField="Css" EnableRTL="true"></ej:Toolbar>

{% endhighlight %}

 ![](RTL_images/RTL_img1.png) 



