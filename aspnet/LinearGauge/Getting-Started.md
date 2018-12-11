---
layout: post
title: Getting Started | LinearGauge | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Linear Gauge
documentation: ug
---

# Getting Started

This section briefly explains on how to create a Linear Gauge control for your application.

* The ASP.NET Linear Gauge provides support to display the Linear Gauge within your web page and allows you to customize it. This section encompasses the details on how to configure Linear Gauge. 
* You will learn how to provide data for a Linear Gauge and display that data in the required way. In addition, you will learn how to customize the default Linear Gauge appearance for your requirements. 



![](Getting-Started_images/Getting-Started_img1.png)

Analog thermometer
{:.caption}

## Create a Linear Gauge

ASP.NET Linear Gauge widget basically renders with flexible API’s. You can easily create the Linear Gauge widget by using simple code example as follows.

1. First create an ASP Project and add necessary Dll’s and Scripts with the help of the given ASP-Getting Started Documentation.
2. Configure web.config files for assemblies

   * The following assemblies references are added properly in web.config file.  

   ~~~ html	
	
		<compilation debug="true" targetFramework="4.5">
		
			<assemblies>
			
				<add assembly="Syncfusion.EJ.Web, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
				
				<add assembly="Syncfusion.EJ, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
				
			</assemblies>
			
		</compilation>	
		
		<httpRuntime targetFramework="4.5" />
		
		<pages> 
		
			<controls>
			
				<add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ.Web, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
				
				<add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
				
				<add  namespace="Syncfusion.JavaScript.DataVisualization.Models" assembly="Syncfusion.EJ" tagPrefix="ej"/>
				
			</controls>
			
		</pages>	
		
   ~~~

3. Adding Script Reference,
    
By default, Syncfusion JavaScript source files has been included into the EJ.Web assembly as an embedded source. So we no need to refer jQuery and Syncfusion scripts externally. For debugging purpose want to refer script files externally, set false to **LoadEJResourcesFromAssembly** in Web.config file as shows in the below image and refer jQuery and Syncfusion script files.

![](Getting-Started_images/Getting-Started_img12.png)

{% highlight html %}


    <!--  jquery script  -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <!-- Essential JS UI widget -->
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>

{% endhighlight %}

N> If you are using the Essential Studio below 13.4.0.53 version, then you need to refer **jQuery.globalize.js** script file along with the above references to render the linear gauge control.

4. Add the mentioned code example to the corresponding designer page to render the Linear Gauge.


{% highlight html %}

<ej:LinearGauge runat="server" ID="thermoLinear">

</ej:LinearGauge>

{% endhighlight %}

Run the above code to get a default Linear Gauge with default values as follows.

![](Getting-Started_images/Getting-Started_img2.png)



### Set Height and Width values

Basic attributes of each canvas elements are height and width. You can set the height and width of the gauge using the following code example.It sets the height and width of the canvas image where the thermometer is to be rendered.

{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500">

</ej:LinearGauge>

{% endhighlight %}

Run the above code to get a gauge that is similar to default. Here height and width of the canvas are set for given values.

![](Getting-Started_images/Getting-Started_img3.png)



### Set Animation option and Label Color

* You can draw the Thermometer with some Label color and Animation.
* Initially set EnableAnimation property to ‘false’ to avoid unwanted script loads.

{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

</ej:LinearGauge>

{% endhighlight %}






Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img4.png)



### Provide scale values

* The scale must have the appearance of a thermometer. By giving ScaleType as Thermometer, you can render a thermometer design.
* Minimum temperature can go up to -10 and maximum body temperature can rise up to 110, so you can give minimum scale value as -10 and maximum value as 110.
* Set the location values such as vertical and horizontal position of the thermometer and give the thermometer height as Length.
* You can give the Minor Interval value as 5 to get the exact temperature on the patient.



{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

</ej:Scales>

</Scales>

</ej:LinearGauge>

{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img5.png)



### Add pointers data

In Linear Gauge the two types pointer available are: Marker pointer and Bar pointer.

* Marker pointer is displayed as a pointer device that shows the actual values. But for your thermometer there is no need of marker pointer. So you can hide the marker pointer by giving opacity as 0. 
* Bar pointer acts as a mercury metal that shows the exact temperature of the patient. Set some of the basic properties of the Bar pointer such as Width, BarPointerDistanceFromScale, BarPointerValue and BarPointerBackgroundColor.


{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<MarkerPointerCollection>

<ej:MarkerPointers MarkerOpacity="0">

</ej:MarkerPointers>

</MarkerPointerCollection>

<BarPointerCollection>

<ej:BarPointers BarPointerdistanceFromScale="-0.5"

BarPointerValue="37" Width="10"

BarPointerBackgroundColor="#DB3738">

</ej:BarPointers>

</BarPointerCollection>

<%--Add the labels customization code here-- %>

<%--Add the ticks customization code here-- %>

<%--Add the custom labels customization code here-- %>

</ej:Scales>

</Scales>

</ej:LinearGauge>

{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img6.png)

Linear gauge with pointers
{:.caption}



### Add Label Customization

* For thermometer, you can display the label value in two sides, to get temperature in different scales. For that you can add two label values in an array.
* To display the value around the scales, labels are used. You can customize the label placement, font (including its style and family) and distance from scale.


{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<%--Add the labels customization code here-- %>

<LabelCollection>

<ej:Labels>

<DistanceFromScale X="-13"></DistanceFromScale>

<Font FontFamily="Segoe UI" FontStyle="Normal"

Size="11px"></Font>

</ej:Labels>

<ej:Labels Placement="Far">

<DistanceFromScale X="10"></DistanceFromScale>

</ej:Labels>

</LabelCollection>

<%--Add the ticks customization code here-- %>

<%--Add the custom labels customization code here-- %>

</ej:Scales>

</Scales>

</ej:LinearGauge>

{% endhighlight %}





Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img7.png)



### Add Ticks Details

* Tick style has two values called major interval and minor interval. You can set major ticks with width and height greater than Minor ticks and you can give TickColor for better visibility in light backgrounds.
* Here four tick details are used for both sides having minor and major ticks.To display the tick value add the following code example. 



{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<%--Add the labels customization code here-- %>

<%--Add the ticks customization code here-- %>

<TickCollection>

<ej:LinearTicks Type="MajorInterval" Height="8"

Width="1" Color="#8c8c8c">

<DistanceFromScale Y="-4"></DistanceFromScale>

</ej:LinearTicks>

<ej:LinearTicks Type="MinorInterval" Height="4"

Width="1" Color="#8c8c8c">

<DistanceFromScale Y="-4"></DistanceFromScale>

</ej:LinearTicks>

<ej:LinearTicks Placement="Far" Type="MajorInterval"

Height="8" Width="1" Color="#8c8c8c">

<DistanceFromScale Y="-4"></DistanceFromScale>

</ej:LinearTicks>

<ej:LinearTicks Placement="Far" Type="MinorInterval"

Height="4" Width="1" Color="#8c8c8c">

<DistanceFromScale Y="-4"></DistanceFromScale>

</ej:LinearTicks>

</TickCollection>

<%--Add the custom labels customization code here-- %>

</ej:Scales>

</Scales>

</ej:LinearGauge>

{% endhighlight %}





Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img8.png)



### Add Custom Label Details

* Custom labels are used to specify the texts in the gauge .It can be customized through various properties.
* In order to show the custom labels, change the showIndicators property to ‘true’.Here you can use custom text to display three range descriptions



{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false">

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent"  ShowCustomLabels="true" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<%--Add the labels customization code here-- %>

<%--Add the ticks customization code here-- %>

<%--Add the custom labels customization code here-- %>

<CustomLabelCollection>

<ej:CustomLabel Value="(° C)" Color="#666666" >

<Position X="44" Y="78"/>

<Font FontFamily="Segoe UI" FontStyle="Bold"

Size="12px"></Font>

</ej:CustomLabel>

<ej:CustomLabel Value="(° F)" Color="#666666" >

<Position X="56" Y="78"/>

<Font FontFamily="Segoe UI" FontStyle="Bold"

Size="12px"></Font>

</ej:CustomLabel>

<ej:CustomLabel Color="#666666" >

<Position X="51" Y="90"/>

<Font FontFamily="Segoe UI" FontStyle="Bold"

Size="13px"></Font>

</ej:CustomLabel>

</CustomLabelCollection>

</ej:Scales>

</Scales>

</ej:LinearGauge>

{% endhighlight %}





Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img9.png)



### Change scale Degree to Fahrenheit

Add the function that convert the temperature in degree to Fahrenheit in the label, with an index value of 1.

{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false" DrawLabels="DrawLabel" >

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<%--Add the labels customization code here-- %>

<%--Add the ticks customization code here-- %>

<%--Add the custom labels customization code here-- %>

</ej:Scales>

</Scales>

</ej:LinearGauge>

<script>

function DrawLabel(args) {

if (args.label.index == 1) {

args.style.textValue = (args.label.value * (9 / 5)) + 32;

args.style.font = "Normal 10px Segoe UI";

}

}

</script>

{% endhighlight %}





Run the above code to get the following output.

![](Getting-Started_images/Getting-Started_img10.png)



### Add Custom label for Current Value

Add the function that displays the current temperature value in the custom label.

{% highlight html %}

<ej:LinearGauge ID="LinearGauge1" runat="server" Height="550" Width="500" LabelColor="#8c8c8c" EnableAnimation="false" DrawCustomLabel="DrawCustomLabel" >

<Scales>

<ej:Scales Type="Thermometer" BackgroundColor="transparent" Minimum="-10" Maximum="110" MinorIntervalValue="5" Width="20" Length="355">

<Border Width="0.5"/>

<Position x="50" Y="18"/>

<%--Add the pointers customization code here-- %>

<%--Add the labels customization code here-- %>

<%--Add the ticks customization code here-- %>

<%--Add the custom labels customization code here-- %>

</ej:Scales>

</Scales>

</ej:LinearGauge>

<script>

function DrawCustomLabel(args) {

if (args.customLabelIndex == 2) {

var temp = args.scaleElement.barPointers[0].value;

var faValue = (temp * (9 / 5)) + 32;

if (temp == -10) {

args.style.textValue = "Very Cold Weather" + "(" + faValue.toFixed(1) + "° F)";

}

else if ((temp > -10 && temp < 0) || (temp > 0 && temp < 15)) {

args.style.textValue = "Cool Weather" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp == 0) {

args.style.textValue = "Freezing point of Water" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp >= 15 && temp < 30) {

args.style.textValue = "Room Temperature" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp == 30) {

args.style.textValue = "Beach Weather" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp == 37) {

args.style.textValue = "Body Temperature" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp == 40) {

args.style.textValue = "Hot Bath Temperature" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp > 40 && temp < 100) {

args.style.textValue = "Very Hot Temperature" + " (" + faValue.toFixed(1) + "° F)";

}

else if (temp == 100) {

args.style.textValue = "Boiling point of Water" + " (" + faValue.toFixed(1) + "° F)";

}

}

}

</script>


{% endhighlight %}


The final output is as follows



![](Getting-Started_images/Getting-Started_img11.png)



