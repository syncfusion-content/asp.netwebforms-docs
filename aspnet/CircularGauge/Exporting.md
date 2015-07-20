---
layout: post
title: Exporting
description: exporting
platform: aspnet
control: Circular Gauge
documentation: ug
---

# Exporting

* Circular Gauge has an exporting feature that converts Gauge control into image format and then export in client side. The method API exportImage is used to export the Circular Gauge. 
* It has two arguments such as file name and file format to specify the file name and file formats. For exporting refer the following code example.





[ASP]



&lt;asp:Button ID="Button1" runat="server" Text="Button" OnClientClick="buttonclickevent()" /&gt;



&lt;ej:CircularGauge runat="server" ID="CoreExportGauge" BackgroundColor="transparent"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true" SweepAngle="296" StartAngle="122" Radius="130" ShowScaleBar="true" Size="1" Maximum="120" MajorIntervalValue="20" MinorIntervalValue="10"&gt;

&lt;PointerCap Radius="12"&gt;&lt;/PointerCap&gt;

&lt;Border Width="0.5"&gt;&lt;/Border&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers Value="60" ShowBackNeedle="true" Length="95" Width="7" BackNeedleLength="20"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;TickCollection&gt;

&lt;ej:CircularTicks Type="Major" Height="16" Width="1" DistanceFromScale="2" /&gt;

&lt;ej:CircularTicks Type="Minor" Height="8" Width="1" DistanceFromScale="2" /&gt;

&lt;/TickCollection&gt;





&lt;LabelCollection&gt;

&lt;ej:CircularLabels Type="Major"&gt;&lt;/ej:CircularLabels&gt;



&lt;/LabelCollection&gt;



&lt;RangeCollection&gt;

&lt;ej:CircularRanges DistanceFromScale="-30" StartValue="0" EndValue="70"&gt;

&lt;/ej:CircularRanges&gt;

&lt;ej:CircularRanges BackgroundColor="#fc0606" DistanceFromScale="-30" StartValue="70" EndValue="110"&gt;

&lt;Border Color="#fc0606"&gt;&lt;/Border&gt;

&lt;/ej:CircularRanges&gt;

&lt;ej:CircularRanges BackgroundColor="#f5b43f" DistanceFromScale="-30" StartValue="110" EndValue="120"&gt;

&lt;Border Color="#f5b43f"&gt;&lt;/Border&gt;

&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



&lt;script type="text/javascript" class="jsScript"&gt;

$(function () {

$("#sampleProperties").ejPropertiesPanel();

$("#Button1").ejButton({ width: "100px", click: "buttonclickevent" });

});

function buttonclickevent() {

var FileName = $("#fileName").val();

var FileFormat = $("#ddlExportImage").ejDropDownList("option", "value");

$("#CoreExportGauge").ejCircularGauge("exportImage", FileName, FileFormat);

}

&lt;/script&gt;





Execute the above code to render the following output.

 ![](Exporting_images/Exporting_img1.png) 
{:.image }


