---
layout: post
title: Bullet Graph Dimensions | BulletGraph | ASP.NET Webforms | Syncfusion
description: bullet graph dimensions
platform: aspnet
control: BulletGraph	
documentation: ug
---

# Bullet Graph Dimensions

This section explains you on how to change the dimensions of the Bullet Graph. You can change various dimensions and properties of Bullet Graph like width, height, quantitative scale length, qualitative range size etc. By default, Bullet Graph uses 595 pixel width and 90 pixel height. You can customize width and height of a Bullet Graph using Width and Height properties of Bullet Graph respectively.

## Size
{% highlight html %}

<ej:BulletGraph ID="BulletGraph1" runat="server" Height="100px" RangDataSource="" Width="500px">



        </ej:BulletGraph>


{% endhighlight  %}

In the above code example, width is set as 500 pixel and height is set as 100 pixel. The output of the above code example with dimension 500 * 100 is as follows.



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img1.png)



## Value for performance bar

The feature measure bar value is customized using the Value property. Default value of this property is 0. 
{% highlight html %}

        <ej:BulletGraph ID="BulletGraph1" Value="5" Width="500px" Height="500px" runat="server">



        </ej:BulletGraph>


{% endhighlight %}
The following screenshot displays Bullet Graph with a performance measure value of 5

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img2.png) 



## Comparative measure value

The Comparative measure value is set using ComparativeMeasureValue property. The default value of this property is 0. 
{% highlight html %}



        <ej:BulletGraph ID="BulletGraph1" ComparativeMeasureValue="5" Width="500px" Height="500px" runat="server">



        </ej:BulletGraph>


{% endhighlight  %}
The following screenshot displays Bullet Graph with comparative measure value of 5



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img3.png)





## Theme

Bullet Graph Theme is customized using Theme property. Default value is flatlight. Bullet Graph supports flatlight and flatdark themes. Flatdark theme improves Bullet Graph appearance when background of Bullet Graph container uses dark color like black. 
{% highlight html %}

        <ej:BulletGraph ID="BulletGraph1" Theme="flatdark" Width="500px" Height="500px" runat="server">



        </ej:BulletGraph>

{% endhighlight %}

The following screenshot displays Bullet Graph with flatdark theme



![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img4.png)  


Bullet Graph with theme

## Orientation

Bullet Graph is oriented either horizontally or vertically using Orientation property. Default value of this property is horizontal. 
{% highlight html %}




<ej:BulletGraph ID="BulletGraph1" Orientation="Vertical" Width="100px" Height="550px" FlowDirection="Backward" runat="server">



        </ej:BulletGraph>

{% endhighlight  %}

## Flow direction

The Flow direction of Bullet Graph is customized using FlowDirection property. Default value of this property is Forward. Setting Forward renders Bullet Graph left to right and Backward renders from right to left.
{% highlight html %}



        <ej:BulletGraph ID="BulletGraph1" FlowDirection="Backward" ComparativeMeasureValue="2" Width="500px" Height="500px" runat="server">



        </ej:BulletGraph>

{% endhighlight %}

The following screenshot displays Bullet Graph in a backward direction.

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img5.png) 



## Qualitative range size

Size of the qualitative range is customized using QualitativeRangeSize property. Default value of this property is 32. 
{% highlight html %}



<ej:BulletGraph ID="BulletGraph1" QualitativeRangeSize="50" runat="server">



        </ej:BulletGraph>


{% endhighlight  %}
The following screenshot displays Bullet Graph with Qualitative range of size 50

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img6.png)



## Quantitative scale length

Length of the quantitative scale is customized using QuantitativeScaleLength property. Default value of this property is 475. 
{% highlight html %}



<ej:BulletGraph ID="BulletGraph1" QuantitativeScaleLength="500" runat="server">



</ej:BulletGraph>

{% endhighlight %}

The following screenshot displays Bullet Graph with Quantitative scale length of 500

![](Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img7.png)



