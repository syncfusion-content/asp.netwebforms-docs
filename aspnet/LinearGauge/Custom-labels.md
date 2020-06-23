---
layout: post
title: Custom labels | LinearGauge | ASP.NET Webforms | Syncfusion
description: Learn about custom labels support in Syncfusion ASP.NET Webforms Linear Gauge control and more details.
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Custom labels

Custom labels are the text that can paste in any location of the Linear Gauge. It is used to define the purpose of the gauge.

## Adding Custom label collection

Custom labels collection can be directly added to the scale object. Refer the following code to add custom labels collection in a Linear Gauge control.

{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false">

<Scales>

<ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30">

</ej:BarPointers>

</BarPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%--Setting Customlabel-- %>

<CustomLabelCollection>

<ej:CustomLabel Value="Mathematics Mark">

<Position X="55" Y="97" />

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}





Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img1.png)



## Basic Customization

### Appearance

* You can customize custom labels using the properties like textAngle, color and font. The API textAngle is used to display the custom labels in the specified angles and color attribute is used to display the custom labels in specified color. You can use value attribute to set the text value in the custom labels. 
* To display the custom labels, set showCustomLabels as ‘true’. Font option is also available on the custom labels. The basic three properties of fonts such as size, family and style can be achieved by size, fontStyle and fontFamily. You can adjust the opacity of the label with the property opacity and the value of opacity lies between 0 and 1.

{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false">

<Scales>

<ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30">

</ej:BarPointers>

</BarPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<%--Setting custom label value, color, textangle and opacity-- %>

<CustomLabelCollection>

<ej:CustomLabel Value="Mathematics Mark" Color="red" TextAngle="30" CustomLabelopacity="0.5">

<Position X="55" Y="87" />

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}







Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img2.png)



## Locating the Custom Labels

To set the location of the custom label in Linear Gauge, position property is used. You can position the custom labels in horizontal and vertical axis using X and Y axis respectively.

{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false">

<Scales>

<ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30">

</ej:BarPointers>

</BarPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />                            </ej:LinearTicks>

</TickCollection>

<%--Setting custom label position-- %>

<CustomLabelCollection>

<ej:CustomLabel Value="Mathematics Mark">

<Position X="55" Y="97" />

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>


{% endhighlight %}



Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img3.png)



## Multiple Custom Labels

You can set multiple custom labels in a single Linear Gauge by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.


{% highlight html %}

<%--For Linear gauge rendering-- %>

<ej:LinearGauge runat="server" ID="PointerGauge"  Height="500" width="200" labelColor="grey" EnableAnimation="false">

<Scales>

<ej:Scales BackgroundColor="transparent" ShowMarkerPointers="false" ShowCustomLabels="true"  ShowBarPointers="true">

<Border Color="transparent" Width="0" />

<BarPointerCollection>

<ej:BarPointers Width="10" BarPointerBackgroundColor="#8BABFF" BarPointerValue="91" BarPointerdistanceFromScale="30">

</ej:BarPointers>

</BarPointerCollection>

<TickCollection >

<ej:LinearTicks Type="MajorInterval" Width="2" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Width="1" height="6" Color="#8c8c8c" >

<DistanceFromScale X="7" Y="0" />

</ej:LinearTicks>

</TickCollection>

<CustomLabelCollection>

<%--Setting customlabel1-- %>

<ej:CustomLabel Value="Mathematics Mark" Color="red">

<Position X="55" Y="87" />

</ej:CustomLabel>

<%--Setting customlabel2-- %>

<ej:CustomLabel Value="Marks in %" Color="red" TextAngle="90">

<Position X="15" Y="57" />

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

<Frame BackgroundImageUrl="../Content/images/gauge/Gauge_linear_light.png" />

</ej:LinearGauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img4.png)