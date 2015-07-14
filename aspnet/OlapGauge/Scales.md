---
layout: post
title: Scales
description: scales
platform: aspnet
control: OLAP Gauge
documentation: ug
---

## Scales

Scale is a basic unit of radial gauge. You can customize the gauge scales by using properties such as radius, minimum, scale direction, interval values etc. 

### Resizing the Scale Bar

Radius of the Scale Bar is changed with the help of scaleRadius property and in order to make ScaleBar visible, set showScaleBar property to ‘true’. You can set size of the Scale Bar with the help of scaleBareSize and border width using scaleBorderWidth property. 



[ASP.NET]

  &lt;ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent"&gt;

        &lt;Frame FrameType="HalfCircle"/&gt;

        &lt;Scales&gt;

            &lt;ej:CircularScales ShowRanges="true" Radius="180" ShowScaleBar="true" Size="2"  ShowIndicators="true" ShowLabels="true"&gt;

&lt;Border Width ="2.5" /&gt;

                &lt;PointerCollection&gt;                    

                    &lt;ej:Pointers ShowBackNeedle="true" BackNeedleLength="20"  Length="125" Width="7" &gt;&lt;/ej:Pointers&gt;

                    &lt;ej:Pointers Type="Marker" MarkerType="Diamond" DistanceFromScale="5" Placement="Center" BackgroundColor="#29A4D9" Length="25" Width="15"&gt;&lt;/ej:Pointers&gt;

                &lt;/PointerCollection&gt;

                &lt;TickCollection&gt;

                    &lt;ej:CircularTicks Type="Major" DistanceFromScale="2" Height="16" Width="1" Color="#8c8c8c" /&gt;

                    &lt;ej:CircularTicks Type="Minor" Height="6" Width="1" DistanceFromScale="2" Color="#8c8c8c" /&gt;

                &lt;/TickCollection&gt;

                &lt;LabelCollection&gt;

                    &lt;ej:CircularLabels Color="#8c8c8c"&gt;&lt;/ej:CircularLabels&gt;

                &lt;/LabelCollection&gt;

                &lt;RangeCollection&gt;

                    &lt;ej:CircularRanges DistanceFromScale="-5" BackgroundColor="#fc0606"&gt;

                        &lt;Border Color="#fc0606"/&gt;&lt;/ej:CircularRanges&gt;

                    &lt;ej:CircularRanges DistanceFromScale="-5"&gt;&lt;/ej:CircularRanges&gt;

                &lt;/RangeCollection&gt;

                &lt;CustomLabelCollection&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="290" /&gt;

                        &lt;Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="320" /&gt;

                        &lt;Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="150" /&gt;

                        &lt;Font Size="12px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                &lt;/CustomLabelCollection&gt;   

            &lt;/ej:CircularScales&gt;

        &lt;/Scales&gt;

    &lt;/ej:OlapGauge&gt;



{ ![](Scales_images/Scales_img1.png) | markdownify }
{:.image }


