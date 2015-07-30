---
layout: post
title: Labels
description: labels
platform: common
control: Linear Gauge
documentation: ug
---

# Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Adding label collection 

Label collection can be directly added to the scale object. Refer the following code example to add label collection in a gauge.



[ASP]

&lt;%--For Setting Linear gauge-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" Value="40" enableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true" ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%-- For Adding Label Collection-- %&gt;

&lt;%--Setting Label textcolor-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels TextColor="white"&gt;&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For setting Frame Object-- %&gt;

&lt;Frame InnerWidth="8" OuterWidth="10" backgroundImageUrl="../Content/images/gauge/Gauge_linear_dark1.png" /&gt;



&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.

![](Labels_images/Labels_img1.png)
{:.image }


## Label Customization

Appearance

* Theattribute angle is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property opacity and the values of it lies between 0 and 1.The includeFirstValue is a special property by enabling this property, the first value of the label is not rendered.
* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. Labels are two types such as major and minor.Major type labels are for major interval values and minor type labels are for minor interval values.



[ASP]

&lt;%--For Linear gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" value="40" enableAnimation="false"&gt;

&lt;Scales&gt;

&lt;ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true" ShowBarPointers="true"&gt;

&lt;Border Color="transparent" Width="0" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="10"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%--Setting textcolor, angle, opacity and includeFirstValue-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels TextColor="red" Angle="10" Opacity="0.5" IncludeFirstValue="false"&gt;

&lt;Font Size="12px" FontFamily="Arial" fontStyle="bold"&gt;&lt;/Font&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="7" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For adding frame object-- %&gt;



<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png"/>

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Labels_images/Labels_img2.png)
{:.image }


## Unit text and Positioning

* The unitText property is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kmph. You can also add the unit text in front of the labels. To achieve this use the enumerable property unitTextPosition. 
* Labels can be positioned with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and labels. Placement property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



[ASP]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;ej:LinearGauge runat="server" ID="PointerGauge" value="31" Width="600" height="250" enableAnimation="false" Themes="FlatLight" Orientation="Horizontal" labelColor="black" EnableResize="true"&gt;

&lt;Scales&gt;

&lt;ej:Scales Width="5" Direction="Clockwise" Type="RoundedRectangle" MajorIntervalValue="25" MinorIntervalValue="5" BackgroundColor="white" ShowMarkerPointers="false" ShowCustomLabels="true" ShowBarPointers="true"&gt;

&lt;Border Color="#AEC75F" Width="2" /&gt;

&lt;BarPointerCollection&gt;

&lt;ej:BarPointers Width="4" BarPointerBackgroundColor="red"&gt;&lt;/ej:BarPointers&gt;

&lt;/BarPointerCollection&gt;

&lt;%--Setting Label Collection-- %&gt;

&lt;LabelCollection&gt;

&lt;ej:Labels  Angle="90" UnitText="%"&gt;

&lt;DistanceFromScale X="0" Y="60" /&gt;

&lt;/ej:Labels&gt;

&lt;/LabelCollection&gt;

&lt;TickCollection &gt;

&lt;ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="20" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" &gt;

&lt;DistanceFromScale X="20" Y="0" /&gt;

&lt;/ej:LinearTicks&gt;

&lt;/TickCollection&gt;

&lt;%-- For setting Custom label collection-- %&gt;

&lt;CustomLabelCollection&gt;

&lt;ej:CustomLabel Value="Download in Progress"&gt;

&lt;Position X="49" Y="25" /&gt;

&lt;/ej:CustomLabel&gt;

&lt;/CustomLabelCollection&gt;

&lt;/ej:Scales&gt;

&lt;/Scales&gt;

&lt;%-- For setting Frame Object-- %&gt;

<Frame InnerWidth="8" OuterWidth="10"

BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light1.png" />

&lt;/ej:LinearGauge&gt;



Execute the above code to render the following output.


![](Labels_images/Labels_img3.png)
{:.image }


