---
layout: post
title: Exporting | CircularGauge | ASP.NET Webforms | Syncfusion
description: exporting
platform: aspnet
control: Circular Gauge
documentation: ug
---

# Exporting

* Circular Gauge has an exporting feature that converts Gauge control into image format and then export in client side. The method API `exportImage` is used to export the Circular Gauge. 
* It has two arguments such as **file name** and **file format** to specify the file name and file formats. For exporting refer the following code example.

  {% highlight html %}

        <asp:Button ID="Button1" runat="server" Text="Button" OnClientClick="buttonclickevent()" />

        <ej:CircularGauge runat="server" ID="CoreExportGauge" BackgroundColor="transparent">

        <Scales>

        <ej:CircularScales ShowRanges="true" SweepAngle="296" StartAngle="122" Radius="130" ShowScaleBar="true" Size="1" Maximum="120" MajorIntervalValue="20" MinorIntervalValue="10">

        <PointerCap Radius="12"></PointerCap>

        <Border Width="0.5"></Border>

        <PointerCollection>

        <ej:Pointers Value="60" ShowBackNeedle="true" Length="95" Width="7" BackNeedleLength="20"></ej:Pointers>

        </PointerCollection>

        <TickCollection>

        <ej:CircularTicks Type="Major" Height="16" Width="1" DistanceFromScale="2" />

        <ej:CircularTicks Type="Minor" Height="8" Width="1" DistanceFromScale="2" />

        </TickCollection>

        <LabelCollection>

        <ej:CircularLabels Type="Major"></ej:CircularLabels>

        </LabelCollection>

        <RangeCollection>

        <ej:CircularRanges DistanceFromScale="-30" StartValue="0" EndValue="70">

        </ej:CircularRanges>

        <ej:CircularRanges BackgroundColor="#fc0606" DistanceFromScale="-30" StartValue="70" EndValue="110">

        <Border Color="#fc0606"></Border>

        </ej:CircularRanges>

        <ej:CircularRanges BackgroundColor="#f5b43f" DistanceFromScale="-30" StartValue="110" EndValue="120">

        <Border Color="#f5b43f"></Border>

        </ej:CircularRanges>

        </RangeCollection>

        </ej:CircularScales>

        </Scales>

        </ej:CircularGauge>

        <script type="text/javascript" class="jsScript">

        $(function () {

        $("#sampleProperties").ejPropertiesPanel();

        $("#Button1").ejButton({ width: "100px", click: "buttonClickEvent" });

        });

        function buttonClickEvent() {

        var FileName = $("#fileName").val();

        var FileFormat = $("#ddExportImage").ejDropDownList("option", "value");

        $("#CoreExportGauge").ejCircularGauge("exportImage", FileName, FileFormat);

        }

        </script>
		
{% endhighlight %}

Execute the above code to render the following output.

 ![](Exporting_images/Exporting_img1.png) 



