---
layout: post
title: Public Methods and Events
description: Public Methods and Events in Sunburst Chart.
platform: aspnet 
control: SunburstChart
documentation: ug
---

## Methods


### redraw()

`redraw` the entire sunburst. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

var sun = $("#Sunburst").data("ejSunburstChart");
sun.redraw();

{% endhighlight %}

### destroy ()

`destroy` the sunburst


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

var sun = $("#Sunburst").data("ejSunburstChart");
sun.destroy();

{% endhighlight %}



## Events

### Load

Fires before loading, you can use `Load` event.


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientLoad="onLoad" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onLoad(){
    // Do Something
}

{% endhighlight %}





### PreRender

Fires before rendering sunburst, you can use `PreRender` event. 



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientPreRender="onPreRender" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onPreRender(){
    // Do Something
}

{% endhighlight %}


### Loaded

Fires after rendering sunburst, you can use `Loaded` event.  


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientLoaded="onLoaded" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onLoaded(){
    // Do Something
}

{% endhighlight %}

### DataLabelRendering

Fires before rendering the data label, you can use `DataLabelRendering` event. 


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientDataLabelRendering="onDataLabelRendering" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onDataLabelRendering(){
    // Do Something
}

{% endhighlight %}

### SegmentRendering

Fires before rendering each segment, you can use `SegmentRendering` event. 


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientSegmentRendering="onSegmentRendering" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onSegmentRendering(){
    // Do Something
}

{% endhighlight %}

### TitleRendering

Fires before rendering sunburst title, you can use `TitleRendering` event.  



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientLoaded="onTitleRendering" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onTitleRendering(){
    // Do Something
}

{% endhighlight %}


### TooltipInitialize





Fires during initialization of tooltip, you can use `TooltipInitialize` event.  


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientTooltipInitialize="onTooltipInitialize" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onTooltipInitialize(){
    // Do Something
}

{% endhighlight %}

### PointRegionClick

Fires after clicking the point in sunburst, you can use `PointRegionClick` event. 


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientPointRegionClick="onPointRegionClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onPointRegionClick(){
    // Do Something
}

{% endhighlight %}


### PointRegionMouseMove

Fires while moving the mouse over sunburst points, you can use `PointRegionMouseMove` event. 



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientPointRegionMouseMove="onPointRegionMouseMove" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onPointRegionMouseMove(){
    // Do Something
}

{% endhighlight %}


### DrillDownClick

Fires when clicking the point to perform drilldown, you can use `DrillDownClick` event.  


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientDrillDownClick="onDrillDownClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onDrillDownClick(){
    // Do Something
}

{% endhighlight %}

### DrillDownBack

Fires when resetting drilldown points, you can use `DrillDownBack` event.  


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientDrillDownBack="onDrillDownBack" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onDrillDownBack(){
    // Do Something
}

{% endhighlight %}


### DrillDownReset


Fires after resetting the sunburst points, you can use `DrillDownReset` event.  


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientDrillDownReset="onDrillDownReset" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onDrillDownReset(){
    // Do Something
}

{% endhighlight %}

### LegendItemRendering


Fires before rendering the legend item, you can use `LegendItemRendering` event. 



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientLegendItemRendering="onLegendItemRendering" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onLegendItemRendering(){
    // Do Something
}

{% endhighlight %}

### LegendItemClick


Fires when clicking the legend item, you can use `LegendItemClick` event.



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientLegendItemClick="onLegendItemClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onLegendItemClick(){
    // Do Something
}

{% endhighlight %}


### Click

Fires when clicking the sunburst points, you can use `Click` event.



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientClick="onClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onClick(){
    // Do Something
}

{% endhighlight %}

### DoubleClick

Fires when double clicking the sunburst points, you can use `DoubleClick` event.



{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnClientDoubleClick="onDoubleClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onDoubleClick(){
    // Do Something
}

{% endhighlight %}

### RightClick

Fires when right clicking the sunburst points, you can use `RightClick` event.


{% highlight html %}

<ej:SunburstChart ClientIDMode="Static" OnRightClick="onRightClick" runat="server" ID="Sunburst">

</ej:SunburstChart>

{% endhighlight %}

{% highlight js %}

function onRightClick(){
    // Do Something
}

{% endhighlight %}




