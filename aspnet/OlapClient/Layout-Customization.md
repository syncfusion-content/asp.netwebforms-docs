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


### Tile View

In Tile View representation, both Grid and Chart will be displayed one over the other, in the same layout. 


{% highlight html %}



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

    <DisplaySettings ControlPlacement="Tile" />

</ej:OlapClient>

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img1.png) 



### Tab View

In Tab View representation, both Grid and Chart will be displayed in a separate tab.


{% highlight html %}





<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

     <DisplaySettings ControlPlacement="Tab" />

 </ej:OlapClient>

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img2.png) 



## Default View

After you set defaultView property either to Chart or Grid, the corresponding control is selected for initial view/visualization, within the layout when the OLAPClient control is loaded for the first time. 

### Chart View

To display/visualize Chart control by default, set defaultView to Chart.


{% highlight html %}



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

    <DisplaySettings DefaultView="Chart"/>

</ej:OlapClient>


{% endhighlight %}

 ![](Layout-Customization_images/Layout-Customization_img3.png) 



### Grid View

To display/visualize Grid control by default, set defaultView to Grid.


{% highlight html %}



 <ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

    <DisplaySettings DefaultView="Grid"/>

</ej:OlapClient>

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img4.png) 



## Hide Grid/Chart

### Grid Only

After you set the displayMode option to GridOnly, the Chart is hidden and the data is displayed only in Grid.



{% highlight html %}



 <ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

    <DisplaySettings Mode="GridOnly"/>

</ej:OlapClient>

{% endhighlight  %}


![](Layout-Customization_images/Layout-Customization_img5.png) 



### Chart Only

After you set the displayMode option to ChartOnly, the Grid is hidden and data is displayed only in Chart.



{% highlight html %}



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc">

    <DisplaySettings Mode="ChartOnly"/>

</ej:OlapClient>


{% endhighlight %}

![](Layout-Customization_images/Layout-Customization_img6.png) 



### Both Grid and Chart

After you set the displayMode option to ChartAndGrid, data is displayed in both Grid and Chart.


{% highlight html %}



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser">

    <DisplaySettings Mode="ChartAndGrid"/>

</ej:OlapClient>

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img7.png) 



## Toggle Panel

You are provided with an option to toggle the visibility of Axis Element Builder and Cube Dimension Browser panels in OLAPClient.


{% highlight html %}





<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser"

     <DisplaySettings EnableTogglePanel="true"/>

 </ej:OlapClient>

{% endhighlight %}


![](Layout-Customization_images/Layout-Customization_img8.png) 



## Maximized/Full Screen View

You can maximize OLAP Grid and OLAP Chart to full screen mode inside OLAP Client for a precise view. By selecting Full Screen icon in the toolbar, OLAP Grid and OLAP Chart are maximized depending on the current tab. You can also perform drilldown action in both OLAP Grid and OLAP Chart in the maximized view.



 ![](Layout-Customization_images/Layout-Customization_img9.png) 



{% highlight html %}



<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="Olap Browser">

    <DisplaySettings EnableFullScreen="true"/>

</ej:OlapClient>

{% endhighlight  %}



The following screenshot shows the maximized view of OLAP Grid and OLAP Chart.



![](Layout-Customization_images/Layout-Customization_img10.png) 



