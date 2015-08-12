---
layout: post
title: Exporting
description: exporting
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Exporting

Linear Gauge has an exporting feature that converts Gauge control into image format and then export in client side. The method API exportImage is used to export the LinearGauge. It has two arguments such as file name and file format to specify the file name and file formats. For exporting refer the following code example.	

[ASP]

&lt;asp:Button ID="Button1" runat="server" Text="Button" OnClientClick="buttonclickevent()" /&gt;

&lt;ej:LinearGauge runat="server" ID="CoreExportGauge" Load="loadGaugeTheme" LabelColor="#8c8c8c"&gt;

&lt;%-- For setting scales-- %&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="4" ShowBarPointers="false" ShowRanges="true" Length="310"&gt;

&lt;Border Color="transparent" Width="0"&gt;&lt;/Border&gt;

&lt;Position X="52" Y="50"/&gt;

&lt;%-- For setting Marker Pointers -- %&gt;

&lt;MarkerPointerCollection&gt;

&lt;ej:MarkerPointers Width="10" Length="10" Value="60" MarkerBackgroundColor="#4d4d4d"&gt;

&lt;Border Color="#4d4d4d"&gt;&lt;/Border&gt;

&lt;/ej:MarkerPointers&gt;

&lt;/MarkerPointerCollection&gt;

&lt;%-- For setting labels-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels&gt;&lt;DistanceFromScale X="-13"&gt;&lt;/DistanceFromScale&gt;

&lt;Font FontFamily="Segoe UI" FontStyle="Bold" Size="11px"&gt;&lt;/Font&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;%-- For setting Ticks-- %&gt;

&lt;TickCollection&gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="1" Color="#8c8c8c"/&gt;

&lt;/TickCollection&gt;

&lt;%-- For setting range-- %&gt;

&lt;RangeCollection&gt;

&lt;ej:Ranges StartValue="0" EndValue="50" RangeBackgroundColor="#F6B53F" EndWidth="4" StartWidth="4"&gt;&lt;Border Color="#F6B53F"&gt;&lt;/Border&gt;&lt;/ej:Ranges&gt;

&lt;ej:Ranges StartValue="50" EndValue="100" RangeBackgroundColor="#E94649" EndWidth="4" StartWidth="4"&gt;&lt;Border Color="#E94649"&gt;&lt;/Border&gt;&lt;/ej:Ranges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;/ej:LinearGauge&gt;

&lt;script type="text/javascript" class="jsScript"&gt;

$(function () {

$("#sampleProperties").ejPropertiesPanel();

$("#Button1").ejButton({ width: "100px", click: "buttonclickevent" });

});



function buttonclickevent() {

var FileName = $("#fileName").val();

var FileFormat = $("#ddlImageFormat").ejDropDownList("option", "value");

$("#CoreExportGauge").ejLinearGauge("exportImage", FileName, FileFormat);

}

&lt;/script&gt;





Execute the above code to render the following output.

![](Exporting_images/Exporting_img1.png)
{:.image }


