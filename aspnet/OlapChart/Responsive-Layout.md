---
layout: post
title: Responsive-Layout
description: responsive layout
platform: aspnet
control: OLAP Chart
documentation: ug
---

# Responsive Layout

Responsive layout is aimed at crafting sites to provide an optimal viewing experience - easy reading. It also provides navigation with a minimum of resizing, panning, and scrolling across a wide range of devices from tablet to desktop. To get responsive layout for OLAP Chart, enable IsResponsive API to true. By using this feature, you can achieve an effective view of the OLAP Chart control in all devices including desktops, tablets, mobiles, etc. 


(% highlight html %}

<%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %>



<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" IsResponsive="true">

        <CommonSeriesOptions Tooltip-Visible="true"/>

        <ClientSideEvents Load="loadTheme" />

</ej:OlapChart>
(% endhighlight %}




![](Responsive-Layout_images/Responsive-Layout_img1.png) 





![](Responsive-Layout_images/Responsive-Layout_img2.png) 



