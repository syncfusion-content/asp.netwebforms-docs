---
layout: post
title: Layout
description: layout
platform: aspnet
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the ItemsLayoutMode property of the TreeMap.

There are four different TreeMap layouts such as

* Squarified Layout
* SliceAndDiceAuto Layout
* SliceAndDiceHorizontal Layout
* SliceAndDiceVertical Layout

Squarified Layout

Squarifiedlayout creates rectangles with best aspect ratio.




{% highlight html %}

[ASP]

[ASPX.CS]

  protected void Page_Load(object sender, EventArgs e)

        {

            this.treemap.DataSource = TreeMapPopulationData.GetData();



        }

[ASPX]



&lt;div style="min-height:404px"&gt;

&lt;ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode=” squarified”&gt;



&lt;/ej:Treemap&gt;

&lt;/div&gt;


{% endhighlight %}



{ ![](Layout_images/Layout_img1.png) | markdownify }
{:.image }


SliceAndDiceAuto Layout

SliceAndDiceAuto layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.






{% highlight html %}

[ASPX]



&lt;div style="min-height:404px"&gt;

&lt;ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode = “sliceanddiceauto” &gt;



&lt;/ej:Treemap&gt;

&lt;/div&gt; 


{% endhighlight %}

 ![C:/Users/ApoorvahR/Desktop/1.png](Layout_images/Layout_img2.png) 
{:.image }


SliceAndDiceHorizontal Layout

SliceAndDiceHorizontal layout creates rectangles with high aspect ratio and displays them sorted horizontally.




{% highlight html %}

 [ASPX]

&lt;div style="min-height:404px"&gt;

&lt;ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode= “sliceanddicehorizontal”&gt;



&lt;/ej:Treemap&gt;

&lt;/div&gt; 



{% endhighlight %}


 ![](Layout_images/Layout_img3.png) 
{:.image }


SliceAndDiceVertical Layout

SliceAndDiceVertical layout creates rectangles with high aspect ratio and displays them sorted vertical.




{% highlight html %}

[ASPX]

&lt;div style="min-height:404px"&gt;

&lt;ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemsLayoutMode= “sliceanddicevertical”&gt;

&lt;/ej:Treemap&gt;

&lt;/div&gt; 



{% endhighlight  %}


![](Layout_images/Layout_img4.png) 
{:.image }


