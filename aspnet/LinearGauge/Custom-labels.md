---
layout: post
title: Custom-labels
description: custom labels
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Custom labels

Custom labels are the text that can paste in any location of the Linear Gauge. It is used to define the purpose of the gauge.

## Adding Custom label collection

Custom labels collection can be directly added to the scale object. Refer the following code to add custom labels collection in a Linear Gauge control.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%--Setting Customlabel-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CustomLabel Value="Mathematics Mark"&gt;

&lt;Position X="55" Y="97" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img1.png)
{:.image }


## Basic Customization

Appearance

* You can customize custom labels using the properties like textAngle, color and font. The API textAngle is used to display the custom labels in the specified angles and color attribute is used to display the custom labels in specified color. You can use value attribute to set the text value in the custom labels. 
* To display the custom labels, set showCustomLabels as ‘true’. Font option is also available on the custom labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. You can adjust the opacity of the label with the property opacity and the value of opacity lies between 0 and 1.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%--Setting custom label value, color, textangle and opacity-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CustomLabel Value="Mathematics Mark" Color="red" TextAngle="30" CustomLabelopacity="0.5"&gt;

&lt;Position X="55" Y="87" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;





Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img2.png)
{:.image }


## Locating the Custom Labels

To set the location of the custom label in Linear Gauge, position property is used. You can position the custom labels in horizontal and vertical axis using X and Y axis respectively.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;                            &lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%--Setting custom label position-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CustomLabel Value="Mathematics Mark"&gt;

&lt;Position X="55" Y="97" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;


Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img3.png)
{:.image }


## Multiple Custom Labels

You can set multiple custom labels in a single Linear Gauge by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30"&gt;

&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;CustomLabelCollection&gt;

&lt;%--Setting customlabel1-- %&gt;

&lt;ej:CustomLabel Value="Mathematics Mark" Color="red"&gt;

&lt;Position X="55" Y="87" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;%--Setting customlabel2-- %&gt;

&lt;ej:CustomLabel Value="Marks in %" Color="red" TextAngle="90"&gt;

&lt;Position X="15" Y="57" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" /&gt;

&lt;/ej:LinearGauge&gt;


Execute the above code to render the following output.





![](Custom-labels_images/Custom-labels_img4.png)
{:.image }


