---
layout: post
title: Tooltip
description: tooltip
platform: aspnet
control: OLAP Gauge
documentation: ug
---

# Tooltip

Tooltip provides the information about the OlapGauge when you move the mouse pointer over the control. You can enable it using 
“showtooltip”property.




{% highlight html %}

<ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent" >

        <Scales>

            <ej:CircularScales ShowRanges="true" Radius="150" ShowScaleBar="true" Size="1"  ShowIndicators="true" ShowLabels="true" sho>

                <Border Width ="0.5" />

                <PointerCollection>                    

                    <ej:Pointers Type="Needle" ShowBackNeedle="true" BackNeedleLength="20"  Length="120" Width="7" NeedleType="Triangle" ></ej:Pointers>

                    <ej:Pointers Type="Marker" MarkerType="Diamond" DistanceFromScale="5" Placement="Center" BackgroundColor="#29A4D9" Length="25" Width="15"></ej:Pointers>

                </PointerCollection>

                <TickCollection>

                    <ej:CircularTicks Type="Major" DistanceFromScale="15" Height="16" Width="1" Color="#8c8c8c" />

                    <ej:CircularTicks Type="Minor" DistanceFromScale="2" Height="6" Width="1" Color="#8c8c8c" />

                </TickCollection>

                <LabelCollection>

                    <ej:CircularLabels Color="#8c8c8c"></ej:CircularLabels>

                </LabelCollection>

                <RangeCollection>

                    <ej:CircularRanges DistanceFromScale="-10" BackgroundColor="black" Size="7">

                        <Border Color="red"/></ej:CircularRanges>

                    <ej:CircularRanges DistanceFromScale="-10" Size="7"></ej:CircularRanges>

                </RangeCollection>

                <CustomLabelCollection>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="290" />

                        <Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="320" />

                        <Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                    <ej:CircularCustomLabel Color="red">

                        <Position X="180" Y="150" />

                        <Font Size="12px" FontFamily="Segoe UI" FontStyle="Normal"></Font>

                    </ej:CircularCustomLabel>

                </CustomLabelCollection>   

            </ej:CircularScales>

        </Scales>

    </ej:OlapGauge>

	
{% endhighlight  %}

## Customizing the tooltip using CSS

You can customize the Tooltip by overriding the existing style attributes and referring it in web page.




{% highlight css %}

<style>

.e-olapgauge-tooltip {

  background-color: aqua !important;

  border: 2px solid red !important;

  color: black !important;

  border-radius: 18px!important;

  margin-top: 20px;

  text-align: left;

  font: 12px Segoe UI;

  line-height: 20px;

}

</style>


{% endhighlight %}



 ![](Tooltip_images/Tooltip_img1.png) 



