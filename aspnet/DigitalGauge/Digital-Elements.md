---
layout: post
title: Digital-Elements
description: digital elements
platform: aspnet
control: Digital Gauge
documentation: ug
---

## Digital Elements

Text Customization

* The attribute value refers the text displayed in the Digital Gauge. This text is applicable only for that item instead of all items. Text color is changed by using the property textColor.
* It is possible to align the text inside the Digital Gauge control by using the property textAlign. Two possible values for text align are as follows
1. left
2. right



[ASP]

&lt;ej:DigitalGauge runat="server" ID="DigitalGauge1"&gt;



&lt;Items&gt;

&lt;%-- Adding Text properties --%&gt;

&lt;ej:DigitalGaugeItems TextAlign="Right" Value="STOP"&gt;



&lt;/ej:DigitalGaugeItems&gt;



&lt;/Items&gt;

&lt;/ej:DigitalGauge&gt;



Execute the above code examples to render the DigitalGauge as follows.



{ ![](Digital-Elements_images/Digital-Elements_img1.png) | markdownify }
{:.image }


