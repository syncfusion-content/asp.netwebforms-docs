---
layout: post
title: Events and Methods
description: Learn how to add Events and Methods in Sparkline.
platform: aspnet
control: Sparkline
documentation: ug
---

# Methods and Events

## Methods

### redraw()

This methods redraws the entire sparkline. You can call `redraw()` whenever you update, add or remove points from the data source or whenever you want to refresh the UI.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

// redraw method for sparkline
$("#Sparkline1").ejSparkline("redraw");

{% endhighlight %}

## Events

### Load

The `Load` event is fired before loading the sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientLoad="onLoad">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onLoad(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### Loaded

The `Loaded` event is fired after loaded the sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientLoaded="onLoaded">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onLoaded(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### TooltipInitialize

Fires before rendering trackball tooltip. You can use `TooltipInitialize` event to customize the text displayed in trackball tooltip.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientTooltipInitialize="onTooltipInitialize">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onTooltipInitialize(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### SeriesRendering

Fires before rendering a series. The `SeriesRendering` event is fired for each series in Sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientSeriesRendering="onSeriesRender">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onSeriesRender(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### PointRegionMouseMove

The `PointRegionMouseMove` event is fired when mouse is moved over a point.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientPointRegionMouseMove="onPointMouseMove">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onPointMouseMove(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### PointRegionMouseClick

The `PointRegionMouseClick` event is fired on clicking a point in sparkline. You can use this event to handle clicks made on points.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientPointRegionMouseClick="onPointMouseClick">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onPointMouseClick(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### SparklineMouseMove

The `SparklineMouseMove` is fired on moving mouse over the sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientSparklineMouseMove="onSparklineMouseMove">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onSparklineMouseMove(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### SparklineMouseLeave

The `SparklineMouseLeave` event is fired on moving mouse outside the sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientSparklineMouseLeave="onSparklineMouseLeave">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onSparklineMouseLeave(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### Click

The `Click` event is fired on clicking the sparkline.
{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientClick="onClick">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onClick(sender) {
                //Do something
    }
</script>

{% endhighlight %}

### DoubleClick

The `DoubleClick` event is fired on double clicking the sparkline.



{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientDoubleClick="onDoubleClick">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onDoubleClick(sender) {
                //Do something
    }
</script>

{% endhighlight %}


### RightClick

The `RightClick` event is fired on right clicking the sparkline.



{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server" OnClientRightClick="onRightClick">    
</ej:Sparkline>

{% endhighlight %}

{% highlight js %}

 <script type="text/javascript">
    function onRightClick(sender) {
                //Do something
    }
</script>

{% endhighlight %}