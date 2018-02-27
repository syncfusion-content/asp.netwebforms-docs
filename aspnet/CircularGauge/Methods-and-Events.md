---
layout: post
title: Events-and-Public-Methods
description: events and public methods
platform: aspnet
control: CircularGauge
documentation: ug
---

# Methods and Events

## Public Methods

### Destroying the Circular Gauge

The `destroy` method is used to destroy the **CircularGauge** widget. All events bound using this._on will be unbind automatically and bring the control to pre-init state.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

<script type="text/javascript">
    $("#CoreCircularGauge").ejCircularGauge("destroy");
</script>

{% endhighlight %}

### Getting Back Needle Length

The `getBackNeedleLength` method is used to get the needle length of **CircularGauge**.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({ scales: [{ pointers: [{ showBackNeedle: true }] }] });
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getBackNeedleLength(0, 0);
</script>

{% endhighlight %}

### Getting Custom Label Angle

The `getCustomLabelAngle` method is used to get the angle of custom label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
 
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{customLabels:[{textAngle:30,value:"MyLabel",position:{x:250,y:300},color:"#fc0606",font:{size: "20px", fontFamily: "Arial", fontStyle: "Bold" }}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getCustomLabelAngle(0, 0);
</script>

{% endhighlight %}

### Getting Custom Label value

The `getCustomLabelValue` method is used to get the value of custom label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{customLabels:[{textAngle:30,value:"MyLabel",position:{x:250,y:300},color:"#fc0606",font:{size: "20px", fontFamily: "Arial", fontStyle: "Bold" }}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getCustomLabelValue(0, 0);
</script>

{% endhighlight %}

### Getting Label Angle

The `getLabelAngle` method is used to get angle of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getLabelAngle(0, 0);
</script>

{% endhighlight %}

### Getting Label Distance From Scale

The `getLabelDistanceFromScale` method is used to get the distance value from scale for label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getLabelDistanceFromScale(0, 0);
</script>

{% endhighlight %}

### Getting Label Placement

The `getLabelPlacement` method is used to get placement of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getLabelPlacement(0, 0);
</script>

{% endhighlight %}

### Getting Label Style

The `getLabelStyle` method is used to get style of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getLabelStyle(0, 0);
</script>

{% endhighlight %}

### Getting Major Interval Value

The `getMajorIntervalValue` method is used to get major interval value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMajorIntervalValue(0);
</script>

{% endhighlight %}

### Getting Maker Distance From Scale

The `getMarkerDistanceFromScale` method is used to get distance from scale value of marker.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMarkerDistanceFromScale(0);
</script>

{% endhighlight %}

### Getting Maker Style

The `getMarkerStyle` method is used to get distance from scale value of marker.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMarkerStyle(0, 0);
</script>

{% endhighlight %}

### Getting Maximum Value

The `getMaximumValue` method is used to get maximum value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMaximumValue(0);
</script>

{% endhighlight %}

### Getting Minimum Value

The `getMinimumValue` method is used to get minimum value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMinimumValue(0);
</script>

{% endhighlight %}

### Getting Minor Interval Value

The `getMinorIntervalValue` method is used to get minor interval value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getMinorIntervalValue(0);
</script>

{% endhighlight %}

### Getting Needle Style

The `getNeedleStyle` method is used to get style of needle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getNeedleStyle(0, 0);
</script>

{% endhighlight %}

### Getting Pointer Cap Border Width

The `getPointerCapBorderWidth` method is used to get border width of pointer cap.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerCapBorderWidth(0);
</script>

{% endhighlight %}

### Getting Pointer Cap Radius

The `getPointerCapRadius` method is used to get radius of pointer cap.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerCapRadius(0);
</script>

{% endhighlight %}

### Getting Pointer Length

The `getPointerLength` method is used to get pointer length.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerLength(0, 0);
</script>

{% endhighlight %}

### Getting Pointer Needle Type

The `getPointerNeedleType` method is used to get needle type of pointer.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerNeedleType(0, 0);
</script>

{% endhighlight %}

### Getting Pointer Placement

The `getPointerPlacement` method is used to get placement of pointer.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerPlacement(0, 0);
</script>

{% endhighlight %}

### Getting Pointer Value

The `getPointerValue` method is used to get pointer value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerValue(0, 0);
</script>

{% endhighlight %}

### Getting Pointer Value

The `getPointerWidth` method is used to get pointer width.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getPointerWidth(0, 0);
</script>

{% endhighlight %}

### Getting Range Border Width

The `getRangeBorderWidth` method is used to get border width of range.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangeBorderWidth(0, 0);
</script>

{% endhighlight %}

### Getting Range Distance From Scale

The `getRangeDistanceFromScale` method is used to get range distance from scale.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangeDistanceFromScale(0, 0);
</script>

{% endhighlight %}

### Getting Range End Value

The `getRangeEndValue` method is used to get end value of range.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangeEndValue(0, 0);
</script>

{% endhighlight %}

### Getting Range Position

The `getRangePosition` method is used to get range position.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangePosition(0, 0);
</script>

{% endhighlight %}

### Getting Range Size

The `getRangeSize` method is used to get range size.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangeSize(0, 0);
</script>

{% endhighlight %}

### Getting Range Start Value

The `getRangeStartValue` method is used to get range start value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getRangeStartValue(0, 0);
</script>

{% endhighlight %}

### Getting Scale Bar Size

The `getScaleBarSize` method is used to get scale bar size.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getScaleBarSize(0);
</script>

{% endhighlight %}

### Getting Scale Border Width

The `getScaleBorderWidth` method is used to get border width of scale.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({ scales: [{showScaleBar: true, size: 6, border:{Width: 1.5} }] });
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getScaleBorderWidth(0);
</script>

{% endhighlight %}

### Getting Scale Direction

The `getScaleDirection` method is used to get scale direction.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getScaleDirection(0);
</script>

{% endhighlight %}

### Getting Scale Radius

The `getScaleRadius` method is used to get scale radius.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getScaleRadius(0);
</script>

{% endhighlight %}

### Getting Start Angle

The `getStartAngle` method is used to get start angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getStartAngle(0);
</script>

{% endhighlight %}

### Getting Sub Gauge Location

The `getSubGaugeLocation` method is used to get location of subGauge.

{% highlight html %}
  
<div id="subGauge1"></div> 

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
 
<script>
    $("#subGauge1").ejCircularGauge({backgroundColor: "#f5b43f",scales: [{radius: 150}]});
    $("#CoreCircularGauge").ejCircularGauge({height: 500,width: 500,scales: [{radius: 250,subGauges: [{controlID: "subGauge1",height: 400,width: 200,position: { x: 200, y: 150 }}]}]});
    circulargaugeObj.getSubGaugeLocation(0, 0);
</script>

{% endhighlight %}

### Getting Sweep Angle

The `getSweepAngle` method is used to get sweep angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getSweepAngle(0);
</script>

{% endhighlight %}

### Getting Tick Angle

The `getTickAngle` method is used to get tick angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickAngle(0, 0);
</script>

{% endhighlight %}

### Getting Tick Distance From Scale

The `getTickDistanceFromScale` method is used to get tick distance from scale value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickDistanceFromScale(0, 0);
</script>

{% endhighlight %}

### Getting Tick Height

The `getTickHeight` method is used to get tick height.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickHeight(0, 0);
</script>

{% endhighlight %}

### Getting Tick Placement

The `getTickPlacement` method is used to get tick placement.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickPlacement(0, 0);
</script>

{% endhighlight %}

### Getting Tick Style

The `getTickStyle` method is used to get tick style.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickStyle(0, 0);
</script>

{% endhighlight %}

### Getting Tick Width

The `getTickWidth` method is used to get tick width.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.getTickWidth(0, 0);
</script>

{% endhighlight %}

### Setting IncludeFirstValue

The `includeFirstValue` method is used to set includeFirstValue.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.includeFirstValue(0, 0, false);
</script>

{% endhighlight %}

### Redrawing Circular Gauge

The `redraw` method is used to redraw the Circular Gauge widget.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.redraw("scale");
</script>

{% endhighlight %}

### Setting Back Needle Length

The `setBackNeedleLength` method is used to set the needle length of **CircularGauge**.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({ scales: [{ pointers: [{ showBackNeedle: true }] }] });
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setBackNeedleLength(0, 0, 10);
</script>

{% endhighlight %}

### Setting Custom Label Angle

The `setCustomLabelAngle` method is used to set the angle of custom label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
 
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{customLabels:[{value:"MyLabel",position:{x:250,y:300},color:"#fc0606",font: { size: "20px", fontFamily: "Arial", fontStyle: "Bold" }}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setCustomLabelAngle(0, 0, 10);
</script>

{% endhighlight %}

### Setting Custom Label value

The `setCustomLabelValue` method is used to set the value of custom label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{customLabels:[{value:"MyLabel",position:{x:180,y:300},color:"#fc0606",font:{size: "20px", fontFamily: "Arial", fontStyle: "Bold" }}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setCustomLabelValue(0, 0, "CircularGauge");
</script>

{% endhighlight %}

### Setting Label Angle

The `setLabelAngle` method is used to set angle of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setLabelAngle(0, 0, 10);
</script>

{% endhighlight %}

### Setting Label Distance From Scale

The `setLabelDistanceFromScale` method is used to set the distance value from scale for label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setLabelDistanceFromScale(0, 0, 10);
</script>

{% endhighlight %}

### Setting Label Placement

The `setLabelPlacement` method is used to set placement of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setLabelPlacement(0, 0, 'far');
</script>

{% endhighlight %}

### Setting Label Style

The `setLabelStyle` method is used to set style of label.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setLabelStyle(0, 0, 'major');
</script>

{% endhighlight %}

### Setting Major Interval Value

The `setMajorIntervalValue` method is used to set major interval value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMajorIntervalValue(0, 10);
</script>

{% endhighlight %}

### Setting Maker Distance From Scale

The `setMarkerDistanceFromScale` method is used to set distance from scale value of marker.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMarkerDistanceFromScale(0, 10);
</script>

{% endhighlight %}

### Setting Maker Style

The `setMarkerStyle` method is used to set distance from scale value of marker.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMarkerStyle(0, 0, 'rectangle');
</script>

{% endhighlight %}

### Setting Maximum Value

The `setMaximumValue` method is used to set maximum value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMaximumValue(0, 130);
</script>

{% endhighlight %}

### Setting Minimum Value

The `setMinimumValue` method is used to set minimum value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMinimumValue(0, 10);
</script>

{% endhighlight %}

### Setting Minor Interval Value

The `setMinorIntervalValue` method is used to set minor interval value of CircularGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setMinorIntervalValue(0, 2);
</script>

{% endhighlight %}

### Setting Needle Style

The `setNeedleStyle` method is used to set style of needle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setNeedleStyle(0, 0, 'arrow');
</script>

{% endhighlight %}

### Setting Pointer Cap Border Width

The `setPointerCapBorderWidth` method is used to set border width of pointer cap.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerCapBorderWidth(0, 5);
</script>

{% endhighlight %}

### Setting Pointer Cap Radius

The `setPointerCapRadius` method is used to set radius of pointer cap.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerCapRadius(0, 10);
</script>

{% endhighlight %}

### Setting Pointer Length

The `setPointerLength` method is used to set pointer length.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerLength(0, 0, 90);
</script>

{% endhighlight %}

### Setting Pointer Needle Type

The `setPointerNeedleType` method is used to set needle type of pointer.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerNeedleType(0, 0, 'triangle');
</script>

{% endhighlight %}

### Setting Pointer Placement

The `setPointerPlacement` method is used to set placement of pointer.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerPlacement(0, 0,'near');
</script>

{% endhighlight %}

### Setting Pointer Value

The `setPointerValue` method is used to set pointer value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerValue(0, 0, 10);
</script>

{% endhighlight %}

### Setting Pointer Value

The `setPointerWidth` method is used to set pointer width.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setPointerWidth(0, 0, 10);
</script>

{% endhighlight %}

### Setting Range Border Width

The `setRangeBorderWidth` method is used to set border width of range.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangeBorderWidth(0, 0, 5);
</script>

{% endhighlight %}

### Setting Range Distance From Scale

The `setRangeDistanceFromScale` method is used to set range distance from scale.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangeDistanceFromScale(0, 0, 10);
</script>

{% endhighlight %}

### Setting Range End Value

The `setRangeEndValue` method is used to set end value of range.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangeEndValue(0, 0, 70);
</script>

{% endhighlight %}

### Setting Range Position

The `setRangePosition` method is used to set range position.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangePosition(0, 0, 'far');
</script>

{% endhighlight %}

### Setting Range Size

The `setRangeSize` method is used to set range size.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangeSize(0, 0, 10);
</script>

{% endhighlight %}

### Setting Range Start Value

The `setRangeStartValue` method is used to set range start value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({scales: [{showRanges: true,ranges: [{distanceFromScale: -30,startValue: 0,endValue: 70}]}]});
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setRangeStartValue(0, 0, 10);
</script>

{% endhighlight %}

### Setting Scale Bar Size

The `setScaleBarSize` method is used to set scale bar size.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setScaleBarSize(0, 160);
</script>

{% endhighlight %}

### Setting Scale Border Width

The `setScaleBorderWidth` method is used to set border width of scale.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge({ scales: [{showScaleBar: true, size: 6, border:{Width: 1.5} }] });
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setScaleBorderWidth(0, 3);
</script>

{% endhighlight %}

### Setting Scale Direction

The `setScaleDirection` method is used to set scale direction.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setScaleDirection(0, 'clockwise');
</script>

{% endhighlight %}

### Setting Scale Radius

The `setScaleRadius` method is used to set scale radius.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setScaleRadius(0, 140);
</script>

{% endhighlight %}

### Setting Start Angle

The `setStartAngle` method is used to set start angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setStartAngle(0, 10);
</script>

{% endhighlight %}

### Setting Sub Gauge Location

The `setSubGaugeLocation` method is used to set location of subGauge.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<div id="subGauge1"></div> 
 
<script>
    $("#subGauge1").ejCircularGauge({backgroundColor: "#f5b43f",scales: [{radius: 150}]});
    $("#CoreCircularGauge").ejCircularGauge({height: 500,width: 500,scales: [{radius: 250,subGauges: [{controlID: "subGauge1",height: 400,width: 200,position: { x: 200, y: 150 }}]}]});
    circulargaugeObj.setSubGaugeLocation(0, 0, {x:50,y:100});
</script>

{% endhighlight %}

### Setting Sweep Angle

The `setSweepAngle` method is used to set sweep angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setSweepAngle(0, 220);
</script>

{% endhighlight %}

### Setting Tick Angle

The `setTickAngle` method is used to set tick angle.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickAngle(0, 0, 10);
</script>

{% endhighlight %}

### Setting Tick Distance From Scale

The `setTickDistanceFromScale` method is used to set tick distance from scale value.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickDistanceFromScale(0, 0, 15);
</script>

{% endhighlight %}

### Setting Tick Height

The `setTickHeight` method is used to set tick height.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickHeight(0, 0, 10);
</script>

{% endhighlight %}

### Setting Tick Placement

The `setTickPlacement` method is used to set tick placement.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickPlacement(0, 0, 'near');
</script>

{% endhighlight %}

### Setting Tick Style

The `setTickStyle` method is used to set tick style.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickStyle(0, 0, 'minor');
</script>

{% endhighlight %}

### Setting Tick Width

The `setTickWidth` method is used to set tick width.

{% highlight html %}

<ej:CircularGauge runat="server" ID="CoreCircularGauge">
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}
  
<script>
    $("#CoreCircularGauge").ejCircularGauge();
    var circulargaugeObj = $("#CoreCircularGauge").data("ejCircularGauge");
    circulargaugeObj.setTickWidth(0, 0, 5);
</script>

{% endhighlight %}


## Events

### Draw Custom Label

The `OnClientDrawCustomLabel` event is triggered while custom labels are drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawCustomLabel="onDrawCustomLabel"> 
</ej:CircularGauge>

{% endhighlight %} 
     
{% highlight js %}   
     
     function onDrawCustomLabel(sender) {
        // do something
      }

{% endhighlight %}

### Draw Indicators

The `OnClientDrawIndicators` event is triggered while indicators are being drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawIndicators="onDrawIndicators"> 
</ej:CircularGauge>

{% endhighlight %} 

{% highlight js %}

    function onDrawIndicators(sender) { 
        // do something
    }

{% endhighlight %}

### Draw Labels

The `OnClientDrawLabels` event is triggered while labels are being drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawLabels="onDrawLabels"> 
</ej:CircularGauge>

{% endhighlight %} 

{% highlight js %}

    function onDrawLabels(sender) { 
        // do something
    }

{% endhighlight %}

### Draw Pointer Cap

The `OnClientDrawPointerCap` event is triggered while pointer cap is being drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawPointerCap="onDrawPointerCap"> 
</ej:CircularGauge>

{% endhighlight %} 

{% highlight js %}

    function onDrawPointerCap(sender) { 
        // do something
    }

{% endhighlight %}

### Draw Pointers

The `OnClientDrawPointers` event is triggered while pointer cap is being drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawPointers="onDrawPointers"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onDrawPointers(sender) { 
        // do something
    }

{% endhighlight %}

### Draw Range

The `OnClientDrawRange` event is triggered when ranges starts to be drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawRange="onDrawRange"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onDrawRange(sender) { 
        // do something
    }

{% endhighlight %}

### Draw Ticks

The `OnClientDrawTicks` event is triggered when ticks are being drawn on the gauge. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDrawTicks="onDrawTicks"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onDrawTicks(sender) { 
        // do something
    }

{% endhighlight %}

### Load

The `OnClientLoad` event is triggered when gauge starts to load. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientLoad="onLoad"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onLoad(sender) { 
        // do something
    }

{% endhighlight %}

### Mouse Click

The `OnClientMouseClick` event is triggered when left mouse button is clicked. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientMouseClick="onMouseClick"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onMouseClick(sender) { 
        // do something
    }

{% endhighlight %}

### Mouse Click Move

The `OnClientMouseClickMove` event is triggered when clicking and dragging the mouse pointer over the gauge pointer. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientMouseClickMove="onMouseClickMove"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onMouseClickMove(sender) { 
        // do something
    }

{% endhighlight %}

### Mouse Click Up

The `OnClientMouseClickUp` event is triggered when clicking and dragging the mouse pointer over the gauge pointer. 

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientMouseClickUp="onMouseClickUp"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onMouseClickUp(sender) { 
        // do something
    }

{% endhighlight %}

### Render Complete

The `OnClientRenderComplete` event is triggered when rendering of the gauge is completed.

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientRenderComplete="onRenderComplete"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onRenderComplete(sender) { 
        // do something
    }

{% endhighlight %}

### Range Mouse Move

The `OnClientRangeMouseMove` event is triggered when moving mouse on ranges.

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientRangeMouseMove="onRangeMouseMove"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onRangeMouseMove(sender) { 
        // do something
    }

{% endhighlight %}

### DoubleClick

The `DoubleClick` event is triggered when double clicking the gauges.

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientDoubleClick="onDoubleClick"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onDoubleClick(sender) { 
        // do something
    }

{% endhighlight %}

### RightClick

The `RightClick` event is triggered when right clicking the gauges.

{% highlight html %}

<ej:CircularGauge ID="ScaleCircularGauge" runat="server" OnClientRightClick="onRightClick"> 
</ej:CircularGauge>

{% endhighlight %}

{% highlight js %}

    function onRightClick(sender) { 
        // do something
    }

{% endhighlight %}