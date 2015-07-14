---
layout: post
title: Tooltip
description: tooltip
platform: aspnet
control: Circular Gauge
documentation: ug
---

## Tooltip

* Tooltip feature has been added to the Circular Gauge. Circular Gauge has several elements such as pointers, label, customLabel, scales, etc.  
* There is a need for Tooltip feature in the Circular Gauge control because whenever the text hides or overrides with other gauge elements, it may not be fully visible. For resolving those problems Tooltip feature has been implemented in the Circular Gauge control.
### Default Tooltip

* Tooltip has three attributes in it. The first two attributes such as showLabelTooltip and showCustomLabelTooltip are for enabling the Tooltip for label as well as custom label in default appearance. 
* ShowLabelTooltip is to enable the Tooltip for labels and showCustomLabelTooltip is for enabling the Tooltip option for customLabels.



[ASPX]

&lt;ej:circulargauge runat=”server” id=”circularGaugeTooltip” backgroundcolor=”transparent” enableAnimation=”false”&gt;



&lt;%-- Defines the tooltip object-- %&gt;

&lt;Tooltip ShowCustomLabelTooltip=”true” ShowLabelTooltip=”true” /&gt;



&lt;%-- Customizes the scale options-- %&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowLabels=”true” Radius="130" &gt;



&lt;PointerCollection&gt;

&lt;ej:Pointers Value=”60” Length=”95” &gt;

&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;



&lt;%-- Customizes the custom label options-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel Value=”0 9 5 3 4 5”&gt;

&lt;Font FontFamily ="Arial" FontStyle="Bold" Size="20px" /&gt;

&lt;Position X ="180" Y="200" /&gt;

&lt;/ej:CircularCustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:circulargauge&gt;



Execute the above code to render the following output.

{ ![](Tooltip_images/Tooltip_img1.png) | markdownify }
{:.image }




### Tooltip Template

In Tooltip option, you can customize the Tooltip window by adding the tooltip template on that page with the help of API TemplateID. Refer to the following code example to know more about Tooltip template.



[ASPX]



&lt;ej:circulargauge runat=”server” id=”circularGaugeTooltip” backgroundcolor=”transparent” nableAnimation=”false”&gt;



&lt;%-- Defines the tooltip object-- %&gt;

<Tooltip



&lt;%-- Enables the custom label tooltip-- %&gt;

ShowCustomLabelTooltip=”true”



&lt;%-- Enables the label tooltip-- %&gt;

ShowLabelTooltip=”true”



&lt;%-- Enables the Tooltip Template-- %&gt;

TemplateID=”Tooltip”/>



&lt;%-- Customizes the scale options-- %&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowLabels=”true” Radius="130" &gt;



&lt;%-- Customizes the pointers options-- %&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers Value=”60” Length=”95” &gt;

&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;



&lt;%-- Customizes the custom label options-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel Value=”0 9 5 3 4 5”&gt;

&lt;Font FontFamily ="Arial" FontStyle="Bold" Size="20px" /&gt;

&lt;Position X ="180" Y="200" /&gt;

&lt;/ej:CircularCustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:circulargauge&gt;


Execute the above code to render the following output.



{ ![](Tooltip_images/Tooltip_img2.png) | markdownify }
{:.image }






