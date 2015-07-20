---
layout: post
title: Responsive-Layout
description: responsive layout
platform: aspnet
control: OLAP Client
documentation: ug
---

# Responsive Layout

Responsive layout is aimed at crafting sites to provide an optimal viewing experience - easy reading. It also provides navigation with a minimum of resizing, panning, and scrolling across a wide range of devices from tablet to desktop. To get responsive layout for OLAP Client, enable IsResponsive API to true. By using this feature, you can achieve an effective view of the OLAP Client control in all devices including desktops, tablets, mobiles, etc. 





{% highlight html %}


[ASPX]

&lt;%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %&gt;



&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" IsResponsive="true"&gt;

        &lt;ClientSideEvents  ChartLoad="setChartProperties" /&gt;

&lt;/ej:OlapClient&gt;



&lt;script type="text/javascript"&gt;

        function setChartProperties(args) {

            this.model.load = "loadTheme";

        }

&lt;/script&gt;


{% endhighlight %}

![](Responsive-Layout_images/Responsive-Layout_img1.png) 
{:.image }


![](Responsive-Layout_images/Responsive-Layout_img2.png) 
{:.image }




![](Responsive-Layout_images/Responsive-Layout_img3.png) 
{:.image }




 ![](Responsive-Layout_images/Responsive-Layout_img4.png) 
{:.image }


