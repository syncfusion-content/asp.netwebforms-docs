---
layout: post
title: Title
description: title
platform: aspnet
control: OLAP Chart
documentation: ug
---

## Title

Title is the area on top of the Chart control that displays the text explaining the OlapChart data. Title text is displayed in a customizable format.  

Setting value to Chart Title

Title property allows you to set the default title for a Chart as follows. 



[ASP.NET]

&lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" title-text="OLAP Chart in Essential Studio"&gt;

 &lt;/ej:OlapChart&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/ChartSettingtitile.png](Title_images/Title_img1.png) | markdownify }
{:.image }


Title Text Customization 

You can customize the title text font using title.font property.



[ASP.NET]

&lt;asp:Content ID="Content1" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

     &lt;ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" title-text="OlapChart in Essential Studio"&gt;

         &lt;ClientSideEvents Load="load" /&gt;

    &lt;/ej:OlapChart&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="Content3" runat="server" ContentPlaceHolderID="ScriptSection"&gt;

&lt;script type="text/javascript"&gt;

        function load(args) {

            this.model.title.font.size = "30px",

            this.model.title.font.fontStyle = "italic",

            this.model.title.font.fontWeight = "bold"

        }

&lt;/script&gt;

&lt;/asp:Content&gt;



{ ![C:/Users/Tamilarasu .M/Pictures/document/Chart/chartTitle.png](Title_images/Title_img2.png) | markdownify }
{:.image }


