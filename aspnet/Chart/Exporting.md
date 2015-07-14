---
layout: post
title: Exporting
description: exporting
platform: aspnet
control: Chart
documentation: ug
---

## Exporting

Essential Chart supports client-side exporting when rendered in canvas mode. The following code snippet illustrates client-side exporting using Essential Chart. 

Code: 

[ASP.NET] 

   &lt;img alt="Export Chart" src="../Content/images/chart/export.png" onclick="onExport()"  title="Export Chart" style="float: right" /&gt;

        &lt;ej:Chart ID="Chart1" EnableCanvasRendering="true" runat="server"&gt;            

        &lt;/ej:Chart&gt; 

&lt;script&gt;

        function onExport() {

            var canvas = $("#container").ejChart("exportChart");

            var image = canvas.toDataURL("image/png")

                              .replace("image/png","image/octet-stream");

            var downloadLink = document.createElement("a");

            downloadLink.href = image;

            downloadLink.download = "Chart.png";

            document.body.appendChild(downloadLink);

            downloadLink.click();

            document.body.removeChild(downloadLink);

    }

&lt;/script&gt;





