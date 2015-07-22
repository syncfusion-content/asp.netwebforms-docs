---
layout: post
title: Layout-Customization
description: layout customization
platform: aspnet
control: OLAP Client
documentation: ug
---

# Layout Customization

OLAP Client UI comes with options to customize the Grid and Chart layout, such as:

1. Default View - Sets the start-up control. 
2. Tab/Tile View – Tab or Tile view to visualize the controls separately or in the same layout. 
3. Hide Grid/Chart - Hides any one of the control by default. 
4. Toggle Panel – Turns On/Off the visibility of Cube Browser and Axis Element Builder panels.  
5. Maximized/Fullscreen view of the control(s) providing a precise view.

## Display View


Tile View

In Tile View representation, both Grid and Chart will be displayed one over the other, in the same layout. 


{% highlight html %}

[ASP.NET]

&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

    &lt;DisplaySettings ControlPlacement="Tile" /&gt;

&lt;/ej:OlapClient&gt;

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img1.png) 
{:.image }


Tab View

In Tab View representation, both Grid and Chart will be displayed in a separate tab.


{% highlight html %}

[ASP.NET]



&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

     &lt;DisplaySettings ControlPlacement="Tab" /&gt;

 &lt;/ej:OlapClient&gt;

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img2.png) 
{:.image }


## Default View

After you set defaultView property either to Chart or Grid, the corresponding control is selected for initial view/visualization, within the layout when the OLAPClient control is loaded for the first time. 

Chart View

To display/visualize Chart control by default, set defaultView to Chart.


{% highlight html %}

[ASP.NET]

&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

    &lt;DisplaySettings DefaultView="Chart"/&gt;

&lt;/ej:OlapClient&gt;


{% endhighlight %}

 ![](Layout-Customization_images/Layout-Customization_img3.png) 
{:.image }


Grid View

To display/visualize Grid control by default, set defaultView to Grid.


{% highlight html %}

[ASP.NET]

 &lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

    &lt;DisplaySettings DefaultView="Grid"/&gt;

&lt;/ej:OlapClient&gt;

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img4.png) 
{:.image }


## Hide Grid/Chart

Grid Only

After you set the displayMode option to GridOnly, the Chart is hidden and the data is displayed only in Grid.



{% highlight html %}

[ASP.NET]

 &lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

    &lt;DisplaySettings Mode="GridOnly"/&gt;

&lt;/ej:OlapClient&gt;

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img5.png) 
{:.image }


Chart Only

After you set the displayMode option to ChartOnly, the Grid is hidden and data is displayed only in Chart.



{% highlight html %}

[ASP.NET]

&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc"&gt;

    &lt;DisplaySettings Mode="ChartOnly"/&gt;

&lt;/ej:OlapClient&gt;


{% endhighlight %}

![](Layout-Customization_images/Layout-Customization_img6.png) 
{:.image }


Both Grid and Chart

After you set the displayMode option to ChartAndGrid, data is displayed in both Grid and Chart.


{% highlight html %}

[ASP.NET]

&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser"&gt;

    &lt;DisplaySettings Mode="ChartAndGrid"/&gt;

&lt;/ej:OlapClient&gt;

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img7.png) 
{:.image }


## Toggle Panel

You are provided with an option to toggle the visibility of Axis Element Builder and Cube Dimension Browser panels in OLAPClient.


{% highlight html %}

[ASP.NET]



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser"

     &lt;DisplaySettings EnableTogglePanel="true"/&gt;

 &lt;/ej:OlapClient&gt;

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img8.png) 
{:.image }


## Maximized/Full Screen View

You can maximize OLAP Grid and OLAP Chart to full screen mode inside OLAP Client for a precise view. By selecting Full Screen icon in the toolbar, OLAP Grid and OLAP Chart are maximized depending on the current tab. You can also perform drilldown action in both OLAP Grid and OLAP Chart in the maximized view.



 ![](Layout-Customization_images/Layout-Customization_img9.png) 
{:.image }


{% highlight html %}

[ASP.NET]

&lt;ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser"&gt;

    &lt;DisplaySettings EnableFullScreen="true"/&gt;

&lt;/ej:OlapClient&gt;

{% endhighlight  %}



The following screenshot shows the maximized view of OLAP Grid and OLAP Chart.



![](Layout-Customization_images/Layout-Customization_img10.png) 
{:.image }


