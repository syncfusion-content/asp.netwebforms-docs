---
layout: post
title: Custom-labels
description: custom labels
platform: aspnet
control: Circular Gauge
documentation: ug
---

## Custom labels

Custom labels are the texts that you can use them in any location of the Gauge.



### Adding Custom Label Collection

Custom labels collection is directly added to the scale object. Refer the following code to add custom labels collection in a Gauge control.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"  &gt;

&lt;Scales&gt;

&lt;ej:CircularScales showLabels="true"&gt;

&lt;%--custom label -- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel TextAngle="10" Color="red" Value="CustomLabel1"&gt;

&lt;Font Size="20px" FontStyle="bold" FontFamily="arial" /&gt;

&lt;Position X="180" Y="100" /&gt;

&lt;/ej:CircularCustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;

Basic Customization

* You can customize Customlabels using the properties such as textAngle, color and font. textAngle attribute is used to display the custom labels in the specified angles and color attribute is used to display the custom labels in specified color. 
* You can use Value attribute to set the text value in the customlabels. To display the custom labels, set showCustomLabels as ‘true’. To set the location of the custom label in Circular Gauge, location property is used. By using x and y axis you can adjust the position of the custom labels.
* Font option is also available on  Customlabels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily attributes. 




[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"  &gt;

&lt;Scales&gt;

&lt;ej:CircularScales size="2" ShadowOffset="10" showRanges="true" ShowScaleBar="true" radius="150" showLabels="true"&gt;

&lt;%--For setting custom label text angle, color, font option, position-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel TextAngle="10" Color="red" Value="CustomLabel1"&gt;

&lt;Font Size="20px" FontStyle="bold" FontFamily="arial" /&gt;

&lt;Position X="180" Y="100" /&gt;

&lt;/ej:CircularCustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.



{ ![](Custom-labels_images/Custom-labels_img1.png) | markdownify }
{:.image }






### Multiple Custom Labels

You can set multiple custom labels in a single Circular Gauge by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.





[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="CircularGauge1"  &gt;

&lt;Scales&gt;

&lt;ej:CircularScales size="2" ShadowOffset="10" showRanges="true" ShowScaleBar="true" radius="150" showLabels="true"&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel TextAngle="10" Color="red" Value="CustomLabel1"&gt;

&lt;Font Size="20px" FontStyle="bold" FontFamily="arial" /&gt;

&lt;Position X="180" Y="100" /&gt;

&lt;/ej:CircularCustomLabel&gt;

&lt;ej:CircularCustomLabel TextAngle="10" Color="green" Value="CustomLabel2"&gt;

&lt;Font Size="20px" FontStyle="bold" FontFamily="arial" /&gt;

&lt;Position X="180" Y="250" /&gt;

&lt;/ej:CircularCustomLabel&gt;



&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

{ ![](Custom-labels_images/Custom-labels_img2.png) | markdownify }
{:.image }


Figure 48: Circular Gauge with multiple custom labels





### Outer Custom Label

* Outer Custom Label is used to show custom labels outside the gauge control. The Outer Custom Label can be positioned with API called outerCustomLabelPosition. The value for this API is enumerable type and its possible values are,
1. Right
2. Left
3. Top
4. Bottom
* When a custom label is to be displayed as an Outer Custom Label, set the API customLabelType as Outer. Refer to the following code example to get the Outer Custom Label.





[ASPX]



<ej:circulargauge runat="server" id="circularGaugeTooltip" backgroundcolor="transparent" enableanimation="false"

OuterCutomLabelPosition="Right">



&lt;%-- Defines the tooltip object-- %&gt;

&lt;Tooltip ShowCustomLabelTooltip="true" ShowLabelTooltip="true" /&gt;



&lt;%-- Customizes the scale options-- %&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowLabels="true" Radius="130" &gt;



&lt;%-- Customizes the pointers options-- %&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers Value="60" Length="95" &gt;

&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;



&lt;%-- Customizes the custom label options-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CircularCustomLabel Value="Average Speed"&gt;

&lt;Font FontFamily ="Arial" FontStyle="Bold" Size="20px" /&gt;

&lt;Position X ="360" Y="30" /&gt;





&lt;/ej:CircularCustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:circulargauge&gt;



Execute the above code to render the following output.

{ ![](Custom-labels_images/Custom-labels_img3.png) | markdownify }
{:.image }




