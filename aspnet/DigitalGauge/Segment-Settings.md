---
layout: post
title: Segment-Settings
description: segment settings
platform: aspnet
control: Digital Gauge
documentation: ug
---

## Segment Settings

### Appearance

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of gradient attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.



[ASP]

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800"&gt;



&lt;Items&gt;



&lt;ej:DigitalGaugeItems Value="GO AHEAD"&gt;

&lt;%-- Adding Basic segment properties --%&gt;

&lt;SegmentSettings Color="Green" Opacity="0.1" Spacing="4"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;/Items&gt;



&lt;/ej:DigitalGauge&gt;



Execute the above code examples to render the DigitalGauge as follows.



{ ![](Segment-Settings_images/Segment-Settings_img1.png) | markdownify }
{:.image }




### Dimension Modification

* Digital Gauge consists of several digital segments. Segment is customized with some properties. Color of the segment is set by using color property. Color is either given as string or hexadecimal value. 
* You can add gradient effects to the segments with the help of gradient attribute. The opacity of the segment is also adjustable. The space between two  segments are adjusted with spacing property.



[ASP]

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800"&gt;



&lt;Items&gt;



&lt;ej:DigitalGaugeItems Value="WELCOME"&gt;

&lt;%-- Adding Basic segment Dimension --%&gt;

&lt;SegmentSettings Length="3" Width="3"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;/Items&gt;



&lt;/ej:DigitalGauge&gt;



Execute the above code examples to render the DigitalGauge as follows.



{ ![](Segment-Settings_images/Segment-Settings_img2.png) | markdownify }
{:.image }




