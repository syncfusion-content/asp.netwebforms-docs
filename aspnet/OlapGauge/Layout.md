---
layout: post
title: Layout
description: layout 
platform: aspnet
control: OLAP Gauge
documentation: ug
---

## Layout 

The OLAP Gauge control provides support to display multiple gauges in a structured layout. You can customize the layout using the ColumnsCount and RowsCount properties. These properties are used to specify the number of columns and rows for displaying controls.

### Supported Layouts

* Wrap Layout: Based on the available space, gauges are aligned and displayed automatically. 
* Row count: Specifies the number of gauge controls to be displayed row-wise.
* Column count: Specifies the number of gauge controls to be displayed column-wise.
### Layout Customization 


You can customize/limit the number of gauges to be displayed in the table with the help of the rowsCount and columnsCount properties.

### Row Count

You can set the number of gauges to be displayed in row using rowsCount property. By default the value is 0.



[ASP.NET]

&lt;ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent" RowsCount="2"&gt;

        &lt;Scales&gt;

            &lt;ej:CircularScales ShowRanges="true" Radius="150" ShowScaleBar="true" Size="1"  ShowIndicators="true" ShowLabels="true"&gt;

                &lt;Border Width ="0.5" /&gt;

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



{ ![](Layout_images/Layout_img1.png) | markdownify }
{:.image }


### Column Count

You can set the number of gauges to be displayed in column using columnsCount property. By default the value is 0.



[ASP.NET]

&lt;ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent" ColumnsCount="2"&gt;

        &lt;Scales&gt;

            &lt;ej:CircularScales ShowRanges="true" Radius="150" ShowScaleBar="true" Size="1"  ShowIndicators="true" ShowLabels="true"&gt;

                &lt;Border Width ="0.5" /&gt;

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



{ ![](Layout_images/Layout_img2.png) | markdownify }
{:.image }


