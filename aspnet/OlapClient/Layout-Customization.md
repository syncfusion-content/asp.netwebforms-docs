---
layout: post
title: Layout Customization | OLAPClient | ASP.NET | Syncfusion
description: layout customization
platform: aspnet
control: OLAPClient
documentation: ug
---

# Layout Customization

## Display View

### Tab View

In Tab View representation, both Grid and Chart will be displayed in a separate tab.  This could be set using the `ControlPlacement` property under the `DisplaySettings` option.  By default, Tab value is set.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings ControlPlacement="Tab" />
</ej:OlapClient>

{% endhighlight  %}

![](Layout-Customization_images/tabview.png) 

## Tile View

In Tile View representation, both Grid and Chart will be displayed one over the other, in the same layout.  Tile view can be set by using the `ControlPlacement` property under the `DisplaySettings` option.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings ControlPlacement="Tile" />
</ej:OlapClient>

{% endhighlight  %}

![](Layout-Customization_images/tileview.png) 

## Default View

### Grid View

To display Grid control by default, set `DefaultView` property under `DisplaySettings` option to Grid, which is the default value of the property.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings DefaultView="Grid" />
</ej:OlapClient>

{% endhighlight  %}

![](Layout-Customization_images/gridview.png) 

### Chart View

To display Chart control by default, set the property `DefaultView` property to Chart.

![](Layout-Customization_images/chartview.png) 

## Display Mode

### Grid Only

After setting the `Mode` property under `DisplaySettings` option to GridOnly, the Chart is hidden and the data is displayed only in the Grid.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings Mode="GridOnly" />
</ej:OlapClient>

{% endhighlight  %}

![](Layout-Customization_images/gridonlyview.png) 


### Chart Only

After setting the `Mode` property under `DisplaySettings` option to ChartOnly, the Grid is hidden and data is displayed only in the Chart.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings Mode="ChartOnly" />
</ej:OlapClient>

{% endhighlight  %}

![](Layout-Customization_images/chartonlyview.png) 

### Both Chart and Grid

After setting the `Mode` property under `DisplaySettings` option to **ChartAndGrid**, data is displayed in both Grid and Chart.  This is the default value of the property.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings Mode="ChartAndGrid" />
</ej:OlapClient>

{% endhighlight  %}	

![](Layout-Customization_images/chartandgrid.png) 

## Toggle Panel

Toggle panel option lets the user to toggle the visibility of Axis Element Builder and Cube Dimension Browser panels in OlapClient with a use of a button. The button could be added to the control by using the `EnableTogglePanel` property under `DisplaySettings` option.  This property is disabled by default.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings EnableTogglePanel="true" />
</ej:OlapClient>

{% endhighlight  %}	

![](Layout-Customization_images/toggleview.png) 

## Maximized/Full Screen View

Full screen view helps to visualize the PivotGrid and OlapChart controls inside OlapClient precisely according to the browser window size.  By selecting full screen icon in the toolbar, PivotGrid/OlapChart is maximized depending on the selected tab.  Drilldown action can also be performed in both PivotGrid and OlapChart in the maximized view.  This option is enabled by setting the `EnableFullScreen` property under `DisplaySettings` option to true.  The value is false by default.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server">
    <DisplaySettings EnableFullScreen="true" />
</ej:OlapClient>

{% endhighlight  %}	

![](Layout-Customization_images/maximizedview.png) 

The following screenshot shows the maximized view of PivotGrid.

![](Layout-Customization_images/maximizedview1.png) 

## Grid Layout

PivotGrid inside OlapClient control can be rendered in any of the following layouts.

* Normal
* NormalTopSummary
* NoSummaries
* ExcelLikeLayout

The layout is set using the `GridLayout` property. By default, normal layout is set.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server" GridLayout="NoSummaries"></ej:OlapClient>

{% endhighlight  %}	

![](Layout-Customization_images/gridlayout.png) 

## Chart Types

While loading the OlapClient initially, the OlapChart widget can be rendered in any one of the available chart types using the `ChartType` property.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" runat="server" ChartType="Column"></ej:OlapClient>

{% endhighlight  %}	

The `ChartType` property takes Column Chart by default. The types available are Column, Stacking Column, Bar, Stacking Bar, Line, Spline, Step Line, Area, Spline Area, Step Area, Stacking Area, Pie, Funnel and Pyramid.

The Chart Type can also be changed dynamically through the toolbar icon.

![](Layout-Customization_images/charttypes.png) 

![](Layout-Customization_images/linechart.png)  
