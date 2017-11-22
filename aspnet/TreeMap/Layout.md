---
layout: post
title: Layout | TreeMap | ASP.NET | Syncfusion
description: layout
platform: aspnet
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the `ItemsLayoutMode` property of the TreeMap.

There are four different TreeMap layouts such as

* Squarified Layout
* SliceAndDiceAuto Layout
* SliceAndDiceHorizontal Layout
* SliceAndDiceVertical Layout

### Squarified Layout

Squarified layout creates rectangles with best aspect ratio.

{% tabs %}
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

    this.treemap.DataSource = TreeMapPopulationData.GetData();



}

{% endhighlight %}

{% highlight html %}

<div style="min-height:404px">

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode=” squarified”>

</ej:Treemap>

</div>

{% endhighlight %}
{% endtabs %}

![](Layout_images/Layout_img1.png)

### SliceAndDiceAuto Layout

SliceAndDiceAuto layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.


{% highlight html %}

<div style="min-height:404px">

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode = “sliceanddiceauto” >

</ej:Treemap>

</div> 


{% endhighlight %}

![](Layout_images/Layout_img2.png) 

### SliceAndDiceHorizontal Layout

SliceAndDiceHorizontal layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% highlight html %}

<div style="min-height:404px">

    <ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode= “sliceanddicehorizontal”>

    </ej:Treemap>

</div> 

{% endhighlight %}


 ![](Layout_images/Layout_img3.png) 



### SliceAndDiceVertical Layout

SliceAndDiceVertical layout creates rectangles with high aspect ratio and displays them sorted vertical.

{% highlight html %}

<div style="min-height:404px">

    <ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode= “sliceanddicevertical”>

    </ej:Treemap>

</div> 

{% endhighlight  %}


![](Layout_images/Layout_img4.png) 