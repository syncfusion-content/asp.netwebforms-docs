---
layout: post
title: Character Settings | DigitalGauge | ASP.NET Webforms | Syncfusion
description: Learn about character settings support in Syncfusion ASP.NET Webforms Digital Gauge control and more details.
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Character Settings

## Appearance

The opacity of the character is adjustable with the help of opacity property. The space between two characters are adjusted with spacing property as like in the segment settings.



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



![ASPNET DigitalGauge Character-Settings image1](Character-Settings_images/Character-Settings_img1.png)

Digital Gauge control with character setting
{:.caption} 



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

Execute the above code examples to render the DigitalGauge as follows.



![ASPNET DigitalGauge Character-Settings image2](Character-Settings_images/Character-Settings_img2.png)


Digital Gauge control with character type as seven segment
{:.caption} 


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



![ASPNET DigitalGauge Character-Settings image3](Character-Settings_images/Character-Settings_img3.png)

Digital Gauge control with position text based on the background image
{:.caption} 



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



![ASPNET DigitalGauge Character-Settings image4](Character-Settings_images/Character-Settings_img4.png)


Digital Gauge control with shadow option
{:.caption} 



## Font Customization

You can customize the **font** of the text as per your requirement. To customize the font, you have to set `enableCustomFont`. Following font customization options are available.

**Font-family**- used to set the font-family of the text.

**Font-style**- used to set the font-style of the text.

**Font-size**- used to set the font-size of the text.




{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Width="800">



<Items>



<%-- Adding shadow effects --%>



<ej:DigitalGaugeItems Value="WELCOME">



<SegmentSettings Length="3" Width="3"/>


<Font Color="white"  Family="Arial"  Style="Normal" FontSize="12px">


</Font>



</ej:DigitalGaugeItems>



</Items>



</ej:DigitalGauge>

{% endhighlight %}



