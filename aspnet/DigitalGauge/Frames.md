---
layout: post
title: Frames
description: frames
platform: aspnet
control: Digital Gauge
documentation: ug
---

## Frames

### Inner and Outer Width Customization

Frames are space that enclose the Digital Gauge. The inner width of the Frame is the distance between the canvas element and the frame. The outer width is the distance from the frame. The code example to set frame’s innerWidth and outerWidth is as follow. 

[ASP]

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1" Value="WELCOME"&gt;

&lt;%-- Adding Frame properties --%&gt;

&lt;Frame InnerWidth="6" OuterWidth="10"/&gt;



&lt;/ej:DigitalGauge&gt;



Execute the above code examples to render the DigitalGauge as follows.



{ ![](Frames_images/Frames_img1.png) | markdownify }
{:.image }




### Setting Background Image

For a better appearance, you can set the backgroundimage for the Digital Gauge using the property backgroundImageUrl. 



[ASP]

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1" Value="RADAR"&gt;

&lt;%-- Adding background image --%&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/board3.jpg"/&gt;

&lt;Items&gt;



&lt;ej:DigitalGaugeItems&gt;



&lt;%-- Adding gauge position --%&gt;



&lt;Position X="80" Y="10"/&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;/Items&gt;

&lt;/ej:DigitalGauge&gt;



Execute the above code examples to render the DigitalGauge as follows.





{ ![](Frames_images/Frames_img2.png) | markdownify }
{:.image }




