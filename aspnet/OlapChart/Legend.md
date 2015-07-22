---
layout: post
title: Legend
description: legend
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Legend

Legend is a color code that helps to differentiate between chart items. Legend also has labels beside each color to indicate that it applies to information from Series 1, Series 2, and so on.

Legend Symbol

In OlapChart, you can customize the legend symbol with different shapes like rectangle, circle, cross, diamond, pentagon, hexagon, star, ellipse, triangle etc. Default value of legend shape is “Rectangle”.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OlapChart in Essential Studio" &gt;

    &lt;Legend Visible="true" RowCount="3" Shape="star"/&gt;

&lt;/ej:OlapChart&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/Legendshape.png](Legend_images/Legend_img1.png) | markdownify }
{:.image }


Legend Position

You can customize the legend position in top, bottom, left and right position of the Chart. Default value of legend position is “bottom”. 



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OlapChart in Essential Studio" &gt;

    &lt;Legend Visible="true" RowCount="3" Shape="star" Position="top"/&gt;

&lt;/ej:OlapChart&gt;





{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/Legend position.png](Legend_images/Legend_img2.png) | markdownify }
{:.image }


Legend Arrangement

You can align the legend using alignment property of legend. This allows you to align the legend in center, far and near position of Chart Area. The Default value of legend alignment is “Center”.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OlapChart in Essential Studio" &gt;

    &lt;Legend Visible="true" RowCount="3"  Alignment="Near"/&gt;

&lt;/ej:OlapChart&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/legendalignment.png](Legend_images/Legend_img3.png) | markdownify }
{:.image }


Legend Style 

You can draw and customize the outline of Chart legend using border property of legend. Default value of legend border color is “Transparent”.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OlapChart in Essential Studio" &gt;

    &lt;Legend Visible="true" RowCount="3"  Border-color="red" Border-width="2"/&gt;

&lt;/ej:OlapChart&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/legend border.png](Legend_images/Legend_img4.png) | markdownify }
{:.image }


Legend Item 

Legend item is represented by an icon or image and a text. This gets rendered automatically corresponding to each Series in the OlapChart. You can customize the Legend item.



[ASP.NET] 

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OLAP Chart in Essential Studio"&gt;

   &lt;Legend Visible="true" Position="Right" Alignment="Near" ItemStyle-Width=1 /&gt;

&lt;/ej:OlapChart&gt;





{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/legenditemborder.png](Legend_images/Legend_img5.png) | markdownify }
{:.image }


Legend Text

You can customize the legend text - font family, font style, font weight and size using font property of legend. The following code illustrates this.



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Title-Text="OlapChart in Essential Studio" &gt;

    &lt;Legend Visible="true" RowCount="3" Font-FontFamily="Segoe UI" Font-    FontStyle="italic"&gt;&lt;/Legend&gt;

&lt;/ej:OlapChart&gt;



{ ![](Legend_images/Legend_img6.png) | markdownify }
{:.image }


