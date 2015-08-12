---
layout: post
title: Character-Settings
description: character settings
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Character Settings

## Appearance

The opacityof the character is adjustable with the help of opacity property. The space between two characters are adjusted with spacing property as like in the segment settings.



{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



<Items>



<ej:DigitalGaugeItems Value="Syncfusion">

<%-- Adding Basic character properties --%>

<CharacterSettings Opacity="0.3" Spacing="3" />



</ej:DigitalGaugeItems>



</Items>



</ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.



![](Character-Settings_images/Character-Settings_img1.png)





## Count and Type

* The number of text to be displayed can be limited by the attribute called count. In Digital Gauge five different types of characters are supported. They are as follows, 
  
  1. EightCrossEightDotMatrix
  
  2. SevenSegment
  
  3. FourteenSegment
  
  4. SixteenSegment 
  
  5. EightCrossEightSquareMatrix.



     ~~~ html

            <ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



            <Items>



            <ej:DigitalGaugeItems Value="123456789">

            <%-- Adding character count and type --%>

            <CharacterSettings Count="10" Type="SevenSegment" Spacing="10" />



            <SegmentSettings Length="8" Width="1"/>



            </ej:DigitalGaugeItems>



            </Items>



            </ej:DigitalGauge>

     ~~~
     {:.pretty-print }

Execute the above code examples to render the DigitalGauge as follows.



![](Character-Settings_images/Character-Settings_img2.png)





## Text Positioning

The text in the DigitalGauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and the y variable positions the text in the vertical axis.



{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800" Height="300">

<%-- Adding frame background image --%>

<Frame BackgroundImageUrl="../Content/images/gauge/Board1.jpg"/>



<Items>



<ej:DigitalGaugeItems Value="YELLOW">



<%-- Adding gauge position --%>



<Position X="80" Y="10"/>



<SegmentSettings Color="Yellow"/>



</ej:DigitalGaugeItems>



</Items>



</ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.



![](Character-Settings_images/Character-Settings_img3.png)





## Shadow Effects

The text in the Digital Gauge is positioned with position object. This object contains two attributes such as x and y. The x variable positions the text in the horizontal axis and y variable positions the text in the vertical axis.



{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



<Items>



<%-- Adding shadow effects --%>



<ej:DigitalGaugeItems Value="WELCOME" ShadowColor="Yellow"



ShadowBlur="20" ShadowOffsetX="15" ShadowOffsetY="15">



<SegmentSettings Length="3" Width="3"/>



</ej:DigitalGaugeItems>



</Items>



</ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.



![](Character-Settings_images/Character-Settings_img4.png)





