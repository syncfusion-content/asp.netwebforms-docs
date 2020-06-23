---
layout: post
title: Segment Settings | DigitalGauge | ASP.NET Webforms | Syncfusion
description: Learn about segment settings support in Syncfusion ASP.NET Webforms Digital Gauge control and more details.
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Segment Settings

## Appearance

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of gradient attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.



  ~~~ html

        <ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



        <Items>



        <ej:DigitalGaugeItems Value="GO AHEAD">

        <%-- Adding Basic segment properties --%>

        <SegmentSettings Color="Green" Opacity="0.1" Spacing="4"/>



        </ej:DigitalGaugeItems>



        </Items>



        </ej:DigitalGauge>

  ~~~

Execute the above code examples to render the DigitalGauge as follows.



![](Segment-Settings_images/Segment-Settings_img1.png)


Digital Gauge control with segment settings
{:.caption} 


## Dimension Modification

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of gradient attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.

  ~~~ html

        <ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



        <Items>



        <ej:DigitalGaugeItems Value="WELCOME">

        <%-- Adding Basic segment Dimension --%>

        <SegmentSettings Length="3" Width="3"/>



        </ej:DigitalGaugeItems>



        </Items>



        </ej:DigitalGauge>

  ~~~

Execute the above code examples to render the DigitalGauge as follows.



![](Segment-Settings_images/Segment-Settings_img2.png)

Digital Gauge control with segment dimension
{:.caption} 



