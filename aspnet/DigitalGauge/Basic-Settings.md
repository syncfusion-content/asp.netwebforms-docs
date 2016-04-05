---
layout: post
title: Basic Settings | DigitalGauge | ASP.NET Webforms | Syncfusion
description: basic settings
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Basic Settings

## Height and Width Customization

The basic customization for any control is to set the dimension. Here dimension refers to two major attributes such as height and width. The height and width assigned in the control will render the canvas element in the given size. The code example to set height and width is as follow. 

{% highlight html %}

<%-- Adding Control with Width and Height Property --%>

<ej:DigitalGauge runat="server" ID="DigitalGauge1"



Height="200" Width="500" Value="syncfusion">



</ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows. 



![](Basic-Settings_images/Basic-Settings_img1.png)

Digital Gauge control with height and width values
{:.caption} 




## Responsive Layout

* For any display devices, the control will be rendered based on the space available in that device. For this purpose, resizing property is given to the Digital Gauge control. The Digital Gauge renders with a given value. 
* When the browser resize the canvas element checks the dimension with its parent element. If there are any changes in parent dimension, Gauge control will changes the dimension based on its parent element change. This feature is enabled by using the property IsResponsive.

{% highlight c# %}

        <%-- Adding Control with Themes and Resizing property --%>

        <ej:DigitalGauge runat="server" ID="DigitalGauge1" IsResponsive="true">





        </ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows. 



![](Basic-Settings_images/Basic-Settings_img2.png) 

Digital Gauge control with Responsible layout
{:.caption} 



## Themes

Themes give the good appearance to the control. There are two types of Themes available for DigitalGauge as follows

* flatlight
* flatdark

{% highlight html %}

        <%-- Adding Control with Themes and Resizing property --%>

        <ej:DigitalGauge runat="server" ID="DigitalGauge1" IsResponsive="true"



            Themes="FlatDark" Value="LOS ANGELS 40 KM">


        </ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows. 

![](Basic-Settings_images/Basic-Settings_img3.png)

Digital Gauge control with flatdark theme
{:.caption} 



## Setting Txt for Digital Gauge

Digital Gauge is mainly used to display the text in the digital format. We can define the value for the text with the help of value property. It is string data type. The Code example for setting the text is as follows.


{% highlight html %}

<%-- Adding Control with text Value --%>

<ej:DigitalGauge runat="server" ID="DigitalGauge1" Value="GO SLOW">



</ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.



![](Basic-Settings_images/Basic-Settings_img4.png)

Digital Gauge control with text as "GO SLOW"
{:.caption} 