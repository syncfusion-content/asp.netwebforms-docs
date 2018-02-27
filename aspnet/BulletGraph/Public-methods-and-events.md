---
layout: post
title: Public Methods and Events | BulletGraph | ASP.NET Webforms | Syncfusion
description: Public Methods and Events
platform: aspnet
control: BulletGraph	
documentation: ug
---


## Methods


### destroy ()

To destroy the bullet graph


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.destroy();
   
{% endhighlight %}


### redraw()

To redraw the bullet graph


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.redraw();
   
{% endhighlight %}




### setComparativeMeasureSymbol()


To set the value for comparative measure in bullet graph.



{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.setComparativeMeasureSymbol();
   
{% endhighlight %}


### setFeatureMeasureBarValue()


To set the value for feature measure bar.



{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.setFeatureMeasureBarValue();
   
{% endhighlight %}


## Events


### DrawCaption

Fires on rendering the caption of bullet graph.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawCaption="onDrawCaption" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}

function onDrawCaption(){
    // Do Something
}

{% endhighlight %}



### DrawCategory

Fires on rendering the category.



{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawCategory="onDrawCategory" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawCategory(){
    // Do Something
}

{% endhighlight %}


### DrawComparativeMeasureSymbol


Fires on rendering the comparative measure symbol.



{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawComparativeMeasureSymbol="onDrawComparativeMeasureSymbol" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawComparativeMeasureSymbol(){
    // Do Something
}

{% endhighlight %}





### DrawFeatureMeasureBar

Fires on rendering the feature measure bar.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawFeatureMeasureBar="onDrawDrawFeatureMeasureBar" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawFeatureMeasureBar(){
    // Do Something
}

{% endhighlight %}






### DrawIndicator


Fires on rendering the indicator of bullet graph.

{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawIndicator="onDrawIndicator" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawIndicator(){
    // Do Something
}

{% endhighlight %}






### DrawLabels


Fires on rendering the labels.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawLabels="onDrawLabels" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawLabels(){
    // Do Something
}

{% endhighlight %}


### DrawTicks

Fires on rendering the ticks.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawTicks="onDrawTicks" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDrawTicks(){
    // Do Something
}

{% endhighlight %}


### DrawQualitativeRanges


Fires on rendering the qualitative ranges.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDrawQualitativeRanges="onDrawQualitativeRanges" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}


{% highlight js %}
 
function onDrawQualitativeRanges(){
    // Do Something
}

{% endhighlight %}






### Load

Fires on loading bullet graph.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientLoad="onLoad" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onLoad(){
    // Do Something
}

{% endhighlight %}


### Click

Click event fires on clicking the bullet graph.

{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientClick="onClick" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onClick(){
    // Do Something
}

{% endhighlight %}


### DoubleClick

DoubleClick event fires on double clicking the bullet graph.


{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientDoubleClick="onDoubleClick" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onDoubleClick(){
    // Do Something
}

{% endhighlight %}


### RightClick

RightClick event fires on right clicking the bullet graph.

{% highlight html %}

<ej:Bulletgraph ClientIDMode="Static" OnClientRightClick="onRightClick" runat="server" ID="bullet1">

</ej:Bulletgraph>

{% endhighlight %}

{% highlight js %}
 
function onRightClick(){
    // Do Something
}

{% endhighlight %}












