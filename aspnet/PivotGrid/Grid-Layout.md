---
layout: post
title: Grid-Layout
description: grid layout
platform: aspnet
control: PivotGrid
documentation: ug
---

## Grid Layout



> _Note:__This feature is applicable only for OLAP datasource._

GridLayouts customize the position of summary elements in the PivotGrid control. Summary elements can be positioned at the top or bottom of each parent member.

The four kinds of Layouts supported by the PivotGrid are as follows:

* Normal
* Excel-like
* Normal top summary
* No summaries

Normal

The Normal layout is the default Layout of the PivotGrid where the summary cells are positioned at the bottom of each parent member and child members appear next to their parent.



{ ![](Grid-Layout_images/Grid-Layout_img1.png) | markdownify }
{:.image }




[ASP] 

&lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Layout="Normal"&gt;&lt;/ej:PivotGrid&gt;



Excel-like Layout

In the Excel-like layout, the summary cells are positioned at the bottom of the Grid and the child members appear under their parent member with a small indent.



{ ![](Grid-Layout_images/Grid-Layout_img2.png) | markdownify }
{:.image }




[ASP]

&lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Layout="ExcelLikeLayout"&gt;&lt;/ej:PivotGrid&gt;



Normal Top Summary

In the NormalTopSummary Layout, the summary cells are positioned at the top of each parent member and the child member appears next to their parent.

{ ![](Grid-Layout_images/Grid-Layout_img3.png) | markdownify }
{:.image }




[ASP]

&lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Layout="NormalTopSummary"&gt;&lt;/ej:PivotGrid&gt;



No Summaries

In No Summaries Layout, the summary cells are hidden and the child members appear next to their parent member.

{ ![](Grid-Layout_images/Grid-Layout_img4.png) | markdownify }
{:.image }


[ASP]

&lt;ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc" Layout="NoSummaries"&gt;&lt;/ej:PivotGrid&gt;



