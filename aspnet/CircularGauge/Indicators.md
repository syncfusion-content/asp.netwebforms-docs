---
layout: post
title: Indicators
description: indicators
platform: aspnet
control: Circular Gauge
documentation: ug
---

# Indicators

Indicators simply indicates the current status of the pointer. Indicators are in several formats such as in shape format, textual format and image format.



## Adding Indicator Collection 



Indicators collection is directly added to the scale object. Refer the following code to add indicator collection in a Gauge control.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales Showindicators="true" &gt;

&lt;IndicatorCollection&gt;

&lt;ej:CircularIndicators Height="10" width="10" Type="Circle"&gt;

&lt;Position X="185" Y="300" /&gt;

&lt;/ej:CircularIndicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;





Execute the above code to render the following output.

 ![C:/Users/karthigeyan/Desktop/das.png](Indicators_images/Indicators_img1.png)
{:.image }




## Basic Customization

* You can enable indicators by setting showIndicators to ‘true’. The height and width property for the indicators are used to specify the area allocated to the indicator for the width and height respectively. You can use the position collection to position the indicators along x and y axis. 
* Indicators are of several types such as, circle, rectangle, rounded rectangle, text and image. By using the type property you can avail those shapes. For image type imageUrl property is used. 



[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales Showindicators="true" backgroundColor="#5DF243" ShowscaleBar="true"  Size="5" radius="120" MinorIntervalValue="5" &gt;

&lt;Border Width="1.5" Color="black" /&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers BackgroundColor="#5DF243" length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;labelCollection&gt;

&lt;ej:CircularLabels type="major" /&gt;

&lt;/labelCollection&gt;

&lt;IndicatorCollection&gt;

&lt;ej:CircularIndicators Height="10" width="10" Type="Circle" &gt;

&lt;Position X="185" Y="300" /&gt;

&lt;/ej:CircularIndicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

 ![](Indicators_images/Indicators_img2.png)
{:.image }




## State Ranges

* State ranges are used to specify the indicator behavior in the specified region. Use startValue and endValue to set the range bound for the pointer. Whenever the pointer cross the specified region, the indicator attributes are applied for ranges. 
* The backgroundColor and borderColor sets the appearance behavior for the indicators. For text type indicators you can give value for text. And text can be changed whenever the pointer crosses its state range area. There are many basic font options available for the text in the state range such as size, fontStyle and fontFamily.



[ASP]



&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales Showindicators="true" backgroundColor="#5DF243" ShowscaleBar="true"  Size="5" radius="150" MinorIntervalValue="5" &gt;

&lt;Border Width="1.5" Color="black" /&gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers BackgroundColor="#5DF243" length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;IndicatorCollection&gt;



&lt;ej:CircularIndicators Height="10" width="10" Type="Circle" &gt;

&lt;Position X="185" Y="300" /&gt;

&lt;StateRangeCollection&gt; &lt;ej: CircularStateRanges EndValue="100" startValue="0" text="" TextColor="#870505" BackgroundColor="#5DF243" BorderColor="black"&gt;&lt;/ej: CircularStateRanges&gt;&lt;/StateRangeCollection&gt;&lt;%--For setting state range end value, start value, text, text color, background color and bordercolor-- %&gt;

&lt;/ej:CircularIndicators&gt;

&lt;/IndicatorCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

 ![](Indicators_images/Indicators_img3.png)
{:.image }




## Multiple Indicators

You can use multiple indicators for a single Gauge. Each indicator have a list of state ranges. Refer the following code example for multiple Indicators.



[ASP]

&lt;%--For Circular Gauge rendering-- %&gt;

&lt;ej:CircularGauge runat="server" ID="ScaleCircularGauge"&gt;

&lt;Scales&gt;

&lt;ej:CircularScales Showindicators="true" ShowRanges="true"  ShowscaleBar="true"  Size="5" radius="150" MinorIntervalValue="5" &gt;

&lt;PointerCollection&gt;

&lt;ej:Pointers  Value="70"  length="110"&gt;&lt;/ej:Pointers&gt;

&lt;/PointerCollection&gt;

&lt;IndicatorCollection&gt;

&lt;%--indicator1 -- %&gt;

<ej:CircularIndicators Height="10" width="10" Type="Circle"

&lt;Position X="165" Y="300" /&gt;

&lt;StateRangeCollection&gt;

&lt;ej:CircularStateRanges EndValue="50" startValue="0" BackgroundColor="#24F92F" BorderColor="black"&gt;&lt;/ej:CircularStateRanges&gt;

&lt;ej:CircularStateRanges EndValue="50" startValue="100" BackgroundColor="#322C04" BorderColor="black"&gt;&lt;/ej:CircularStateRanges&gt;&lt;/StateRangeCollection&gt;

&lt;/ej:CircularIndicators&gt;

&lt;%--indicator2-- %&gt;

&lt;ej:CircularIndicators Height="10" width="10" Type="Circle" &gt;

&lt;Position X="215" Y="300" /&gt;

&lt;StateRangeCollection&gt;

&lt;ej:CircularStateRanges EndValue="50" startValue="0" BackgroundColor="#600000" BorderColor="black"&gt;&lt;/ej:CircularStateRanges&gt;

&lt;ej:CircularStateRanges EndValue="100" startValue="50" BackgroundColor="#FF4F2A" BorderColor="black"&gt;&lt;/ej:CircularStateRanges&gt;&lt;/StateRangeCollection&gt;

&lt;/ej:CircularIndicators&gt;

&lt;/IndicatorCollection&gt;

&lt;RangeCollection&gt;

&lt;ej:CircularRanges DistanceFromScale="-30" startvalue="0" EndValue="50" BackgroundColor="green" Placement="Far"&gt;&lt;/ej:CircularRanges&gt;

&lt;ej:CircularRanges DistanceFromScale="-30" StartValue="50" EndValue="100" BackgroundColor="red" Placement="Far"&gt;&lt;/ej:CircularRanges&gt;

&lt;/RangeCollection&gt;

&lt;/ej:CircularScales&gt;

&lt;/Scales&gt;

&lt;/ej:CircularGauge&gt;



Execute the above code to render the following output.

 ![](Indicators_images/Indicators_img4.png)
{:.image }


Figure 41: Circular Gauge with multiple indicators

