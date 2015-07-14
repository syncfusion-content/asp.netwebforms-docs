---
layout: post
title: Labels
description:  labels
platform: aspnet
control: Circular Gauge
documentation: ug
---

##  Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.



### Adding Label Collection 

Label collection is directly added to the scale object. Refer the following code example to add label collection in a Gauge.





[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales&gt;

&lt;labelCollection&gt;

&lt;ej:CircularLabels Angle="30"&gt;&lt;/ej:CircularLabels&gt;

&lt;/labelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

{ ![C:/Users/karthigeyan/Desktop/Untitled.png](Labels_images/Labels_img1.png) | markdownify }
{:.image }


        Figure 32(a): Circular Gauge with  label collection

### Label Customization

Appearance

* Theattribute angle is used to display the labels in the specified angles and color attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property opacity and the values of it lies between 0 and 1.
* You can adjust the labels based on the tick’s direction by setting autoAngle as true. includeFirstValue is an special property especially used in some special scenarios such as in clock, where the value 0 needs to be replaced with that of 12. By enabling this property the first value of the label is not rendered.
* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. Labels are two types such as major and minor.Major types labels are for major interval values and minor types labels are for minor interval values. 



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowscaleBar="true" BackgroundColor="#FAF4B5" Size="10" radius="110"&gt;

&lt;Border Width="2" Color="yellow" /&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers Value="40" length="80" width="16" Opacity="0.6" BackgroundColor="#FAF4B5" &gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;%--For setting includefirst value, label color-- %&gt;

&lt;labelCollection&gt;

&lt;ej:CircularLabels Angle="10" Opacity="0.8" IncludeFirstValue="false" color="yellow"&gt;

&lt;Font Size="15px" FontFamily="arial" FontStyle="bold"&gt;&lt;/Font&gt;

&lt;/ej:CircularLabels&gt;

&lt;/labelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;





Execute the above code to render the following output.

{ ![](Labels_images/Labels_img2.png) | markdownify }
{:.image }


Unit text and Position

* unitText is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kmph. You can also add the unit text in front of the labels. You can achieve this by using an enumerable property unitTextPosition. With this you can position the unit text in front or back.
* Labels can be positioned with the help of two properties such as distanceFromScale and placement. distanceFromScale property defines the distance between the scale and labels.  Placement property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.



[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true" ShowscaleBar="true"  Size="2" radius="150"&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers Value="40" showbackneedle="true" length="100"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;labelCollection&gt;

&lt;%--For setting unit text and unit text position-- %&gt;

&lt;ej:CircularLabels unittext="kmpH" UnitTextPosition="back"&gt;

&lt;Font Size="15px" FontFamily="arial" FontStyle="bold"&gt;&lt;/Font&gt;

&lt;/ej:CircularLabels&gt;

&lt;/labelCollection&gt;

&lt;RangeCollection&gt;

&lt;ej:CircularRanges StartValue="0" EndValue="50" backgroundColor="green" Placement="far" DistanceFromScale="-30"&gt;&lt;/ej:CircularRanges&gt;

&lt;ej:CircularRanges StartValue="50" EndValue="80" backgroundColor="yellow" Placement="far" DistanceFromScale="-30"&gt;&lt;/ej:CircularRanges&gt;

&lt;ej:CircularRanges StartValue="80" EndValue="100" backgroundColor="red" Placement="far" DistanceFromScale="-30"&gt;&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

{ ![](Labels_images/Labels_img3.png) | markdownify }
{:.image }










### Multiple Labels

You can achieve multiple labels such as minor and major in a Gauge sample scale. Refer the following code example for multiple labels variation.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales ShowRanges="true" MinorIntervalValue="5" majorintervalvalue="10" backgroundColor="yellow" ShowscaleBar="true"  Size="5" radius="150"&gt;

&lt;PointerCap BackgroundColor="yellow" borderColor="red" BorderWidth="0.5" Radius="10"&gt;&lt;/PointerCap&gt;

&lt;Border Width="1.5" Color="red" /&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers BackgroundColor="yellow" length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;labelCollection&gt;

&lt;%--For setting label1-- %&gt;

&lt;ej:CircularLabels type="minor" Color="yellow" /&gt;

&lt;%--For setting label2-- %&gt;

&lt;ej:CircularLabels type="major" Color="red" /&gt;

&lt;/labelCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;





Execute the above code to render the following output.

{ ![](Labels_images/Labels_img4.png) | markdownify }
{:.image }




