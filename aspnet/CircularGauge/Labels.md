---
layout: post
title: Labels | CircularGauge | ASP.NET Webforms | Syncfusion
description: Learn about labels support in Syncfusion ASP.NET Webforms Circular Gauge control and more details.
platform: aspnet
control: Circular Gauge
documentation: ug
---

#  Labels

Labels are units that are used to display the values in the scales. You can customize `Labels` with the properties like `Angle`, `Color`, `Font`, `Opacity`, etc.


## Adding Label Collection 

Label collection is directly added to the scale object. Refer the following code example to add label collection in a Gauge.

{% highlight html %}


<%--For Circular Gauge rendering-- %>

<ej:CircularGauge runat="server" ID="ScaleCircularGauge">

<Scales>

<ej:CircularScales>

<labelCollection>

<ej:CircularLabels Angle="30"></ej:CircularLabels>

</labelCollection>

</ej:CircularScales>

</Scales>

</ej:CircularGauge>

{% endhighlight %}

Execute the above code to render the following output.

 ![C:/Users/karthigeyan/Desktop/Untitled.png](Labels_images/Labels_img1.png)


## Label Customization

### Appearance

* The attribute `Angle` is used to display the labels in the specified angles and `Color` attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property `Opacity` and the values of it lies between 0 and 1.
* You can adjust the labels based on the tick’s direction by setting `AutoAngle` as true. `IncludeFirstValue` is an special property especially used in some special scenarios such as in clock, where the value 0 needs to be replaced with that of 12. By enabling this property the first value of the label is not rendered.
* `Font` option is also available on the labels. The basic three properties of fonts such as `Size`, `Family` and `Style` can be achieved by size, fontStyle and fontFamily. Labels are two types such as major and minor.Major types labels are for major interval values and minor types labels are for minor interval values.


{% highlight html %}


        <%--For Circular Gauge rendering-- %>

        <ej:CircularGauge runat="server" ID="ScaleCircularGauge">

        <Scales>

        <ej:CircularScales ShowscaleBar="true" BackgroundColor="#FAF4B5" Size="10" radius="110">

        <Border Width="2" Color="yellow" />

        <PointerCollection>

        <ej:Pointers Value="40" length="80" width="16" Opacity="0.6" BackgroundColor="#FAF4B5" ></ej:Pointers>

        </PointerCollection>

        <%--For setting includefirst value, label color-- %>

        <labelCollection>

        <ej:CircularLabels Angle="10" Opacity="0.8" IncludeFirstValue="false" color="yellow">

        <Font Size="15px" FontFamily="arial" FontStyle="bold"></Font>

        </ej:CircularLabels>

        </labelCollection>

        </ej:CircularScales>

        </Scales>

        </ej:CircularGauge>

{% endhighlight %}


Execute the above code to render the following output.

 ![](Labels_images/Labels_img2.png)


### Unit text and Position

* `UnitText` is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. You can achieve this by using an enumerable property `UnitTextPosition`. With this you can position the unit text in front or back.
* Labels can be positioned with the help of two properties such as `DistanceFromScale` and `Placement`. **DistanceFromScale** property defines the distance between the scale and labels.  **Placement** property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.


{% highlight html %}


        <%--For Circular Gauge rendering-- %>

        <ej:CircularGauge runat="server" ID="ScaleCircularGauge">

        <Scales>

        <ej:CircularScales ShowRanges="true" ShowscaleBar="true"  Size="2" radius="150">

        <PointerCollection>

        <ej:Pointers Value="40" showbackneedle="true" length="100"></ej:Pointers>

        </PointerCollection>

        <labelCollection>

        <%--For setting unit text and unit text position-- %>

        <ej:CircularLabels unittext="kmpH" UnitTextPosition="back">

        <Font Size="15px" FontFamily="arial" FontStyle="bold"></Font>

        </ej:CircularLabels>

        </labelCollection>

        <RangeCollection>

        <ej:CircularRanges StartValue="0" EndValue="50" backgroundColor="green" Placement="far" DistanceFromScale="-30"></ej:CircularRanges>

        <ej:CircularRanges StartValue="50" EndValue="80" backgroundColor="yellow" Placement="far" DistanceFromScale="-30"></ej:CircularRanges>

        <ej:CircularRanges StartValue="80" EndValue="100" backgroundColor="red" Placement="far" DistanceFromScale="-30"></ej:CircularRanges>

        </RangeCollection>

        </ej:CircularScales>

        </Scales>

        </ej:CircularGauge>

{% endhighlight %}


Execute the above code to render the following output.

 ![](Labels_images/Labels_img3.png)



## Multiple Labels

You can achieve multiple labels such as minor and major `Type` in a **Gauge** sample scale. Refer the following code example for multiple labels variation.


{% highlight html %}



<%--For Circular Gauge rendering-- %>

<ej:CircularGauge runat="server" ID="ScaleCircularGauge">

<Scales>

<ej:CircularScales ShowRanges="true" MinorIntervalValue="5" majorintervalvalue="10" backgroundColor="yellow" ShowscaleBar="true"  Size="5" radius="150">

<PointerCap BackgroundColor="yellow" borderColor="red" BorderWidth="0.5" Radius="10"></PointerCap>

<Border Width="1.5" Color="red" />

<PointerCollection>

<ej:Pointers BackgroundColor="yellow" length="110"></ej:Pointers>

</PointerCollection>

<labelCollection>

<%--For setting label1-- %>

<ej:CircularLabels type="minor" Color="yellow" />

<%--For setting label2-- %>

<ej:CircularLabels type="major" Color="red" />

</labelCollection>

</ej:CircularScales>

</Scales>

</ej:CircularGauge>

{% endhighlight %}



Execute the above code to render the following output.

 ![](Labels_images/Labels_img4.png)



