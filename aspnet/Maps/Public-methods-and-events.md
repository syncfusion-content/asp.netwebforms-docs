---
layout: post
title: Public Methods and Events | Maps | ASP.NET Webforms | Syncfusion
description: Public Methods and Events
platform: aspnet
control: Maps
documentation: ug
---


## Methods

### navigateTo(latitude, longitude, level)

Method for navigating to specific shape based on latitude, longitude and zoom level, you can use `navigateTo` method.


{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.navigateTo();
   
{% endhighlight %}


### pan(direction)

Method to perform map panning, you can use `pan` method.

{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.pan();
   
{% endhighlight %}

### refresh()

Method to reload the map, you can use `refresh` method.

{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refresh();
   
{% endhighlight %}


### refreshLayers()

Method to reload the shapeLayers with updated values, you can use `refreshLayers` method.


{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refreshLayers();
   
{% endhighlight %}


### refreshNavigationControl(navigation)

Method to reload the navigation control with updated values, you can use `refreshNavigationControl` method.

{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refreshNavigationControl();
   
{% endhighlight %}


### zoom(level, isAnimate)

Method to perform map zooming, you can use `zoom` method.


{% highlight html %}
 
<ej:Map ClientIDMode="Static" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.zoom();
   
{% endhighlight %}



## Events

### MarkerSelected

Triggered on selecting the map markers, you can use `MarkerSelected` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientMarkerSelected="onMarkerSelected" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function onMarkerSelected(){
    // Do Something
}

{% endhighlight %}


### Mouseleave

Triggers while leaving the hovered map shape, you can use `Mouseleave` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientMouseleave="onMouseleave" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function onMouseLeave(){
    // Do Something
}

{% endhighlight %}


### Mouseover

Triggers while hovering the map shape, you can use `mouseover` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientMouseover="onMouseover" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function onMouseOver(){
    // Do Something
}

{% endhighlight %}


### OnRenderComplete

Triggers once map render completed, you can use `OnRenderComplete` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientOnRenderComplete="OnRenderComplete" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function OnRenderComplete(){
    // Do Something
}

{% endhighlight %}


### Panned

Triggers when map panning ends, you can use `Panned` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientPanned="onPanned" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onPanned(){
    // Do Something
}

{% endhighlight %}


### ShapeSelected

Triggered on selecting the map shapes, you can use `ShapeSelected` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientShapeSelected="onShapeSelected" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function onShapeSelected(){
    // Do Something
}

{% endhighlight %}


### ZoomedIn

Triggered when map is zoomed-in, you can use `ZoomedIn` event.


{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientZoomedIn="onZoomedIn" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}

{% highlight js %}
 
function onZoomedIn(){
    // Do Something
}

{% endhighlight %}


### ZoomedOut

Triggers when map is zoomed out, you can use `ZoomedOut` event.


{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientZoomedOut="onZoomedOut" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onZoomedOut(){
    // Do Something
}

{% endhighlight %}


### shapeRendering

Triggers while rendering rendering each shape, you can use `ShapeRendering` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientShapeRendering="onShapeRendering" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onShapeRendering(){
    // Do Something
}

{% endhighlight %}

### bubbleRendering

Triggers while rendering each bubble, you can use `BubbleRendering` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientZoomedOut="onBubbleRendering" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onBubbleRendering(){
    // Do Something
}

{% endhighlight %}


### legendItemRendering

Triggers while rendering each bubble, you can use `LegendItemRendering` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientLegendItemRendering="onLegendItemRendering" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onLegendItemRendering(){
    // Do Something
}

{% endhighlight %}



### Click

Triggers while clicking on the layers of the map, you can use `Click` event.


{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientClick="onClick" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onClick(){
    // Do Something
}

{% endhighlight %}

### DoubleClick

Triggers while double clicking on the layers of the map, you can use `DoubleClick` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientDoubleClick="onDoubleClick" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onDoubleClick(){
    // Do Something
}

{% endhighlight %}

### RightClick

Triggers while right clicking on the layers of the map, you can use `RightClick` event.


{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientRightClick="onRightClick" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onRightClick(){
    // Do Something
}

{% endhighlight %}

### Load

Triggers before loading the map, you can use `Load` event.

{% highlight html %}

<ej:Map ClientIDMode="Static" OnClientLoad="onLoad" runat="server" ID="Map1">

</ej:Map>

{% endhighlight %}


{% highlight js %}
 
function onLoad(){
    // Do Something
}

{% endhighlight %}