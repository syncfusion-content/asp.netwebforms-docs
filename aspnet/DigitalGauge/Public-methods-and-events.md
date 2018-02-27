---
layout: post
title: Public Methods and Events | DigitalGauge | ASP.NET Webforms | Syncfusion
description: Public Methods and Events
platform: aspnet
control: Digital Gauge
documentation: ug
---

## Methods


### destroy()


To `destroy` the digital gauge


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.destroy();
   
{% endhighlight %}


### exportImage(fileName, fileType)


To `export` Digital Gauge as Image

{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.exportImage();
   
{% endhighlight %}


### getPosition(itemIndex)

Gets the location of an item that is displayed on the gauge.


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.getPosition();
   
{% endhighlight %}


### getValue(itemIndex)


ClientSideMethod `getValue` Gets the value of an item that is displayed on the gauge


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}


{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.getValue();
   
{% endhighlight %}



### refresh()


`Refresh` the digital gauge widget



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}


{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.refresh();
   
{% endhighlight %}


### setPosition(itemIndex, value)

ClientSideMethod `Set Position` Sets the location of an item to be displayed in the gauge



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}


{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.setPosition();
   
{% endhighlight %}


### setValue(itemIndex, value)

ClientSideMethod `SetValue` Sets the value of an item to be displayed in the gauge.


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" runat="server" ID="Gauge1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.setValue();
   
{% endhighlight %}




## Events



### Init

Triggers when the gauge is initialized.


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientInit="onInit" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onInit(){
    // Do Something
}

{% endhighlight %}





### ItemRendering

Triggers when the gauge `item rendering`.


{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientItemRendering="onItemRendering" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onItemRendering(){
    // Do Something
}

{% endhighlight %}



### Load


Triggers when the gauge is start to `load`.



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientLoad="onLoad" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onLoad(){
    // Do Something
}

{% endhighlight %}





### RenderComplete


Triggers when the gauge render is completed.



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientRenderComplete="onRenderComplete" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onRenderComplete(){
    // Do Something
}

{% endhighlight %}


### Click

`Click` event triggers on clicking the gauges. 

{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientClick="onClick" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onClick(){
    // Do Something
}

{% endhighlight %}

### DoubleClick

The `DoubleClick` event is triggered when double clicking the gauges.



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientDoubleClick="onDoubleClick" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onDoubleClick(){
    // Do Something
}

{% endhighlight %}


### RightClick

The `RightClick` event is triggered when right clicking the gauges.



{% highlight html %}

<ej:DigitalGauge ClientIDMode="Static" OnClientRightClick="onRightClick" runat="server" ID="bullet1">

</ej:DigitalGauge>

{% endhighlight %}

{% highlight js %}
 
function onRightClick(){
    // Do Something
}

{% endhighlight %}

