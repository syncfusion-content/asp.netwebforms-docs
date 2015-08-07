---
layout: post
title: TreeMap-Elements
description: treemap elements
platform: aspnet
control: TreeMap
documentation: ug
---

# TreeMap Elements

TreeMap contains various elements such as,

* Legend
* Headers
* Labels

## Legend

You can set the color value of leaf nodes using TreeMapLegend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using RangeColorMapping.

You can set ShowLegend propery value to “True” to enable or disable legend visibility.

## TreeMap Legend

You can decide the size of the legend icons by setting IconWidth and IconHeight properties of the TreeMapLegend property avail in TreeMap.

## Label for Legend

You can customize the labels of the legenditem using LegendLabel property of RangeColorMapping. 



{% highlight html %}

[ASP]

[ASPX.CS]

  protected void Page_Load(object sender, EventArgs e)

        {

            this.treemap.DataSource = TreeMapPopulationData.GetData();



        }

 [ASPX]



&lt;div style="min-height:404px"&gt;

    &lt;ej:Treemap ID="treemap" runat="server" ColorValuePath = "Growth" WeightValuePath = "Population" ShowLegend = "true" &gt;

       &lt;TreeMapLegend IconHeight = "17" IconWidth = "17"&gt;&lt;/TreeMapLegend&gt;

        &lt;LeafItemSettings LabelPath = "Country"&gt;&lt;/LeafItemSettings&gt;



         &lt;TreeMapRangeColorMappings&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

        &lt;/TreeMapRangeColorMappings&gt;



        &lt;Levels&gt;

            &lt;ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25"&gt;&lt;/ej:TreeMapLevel&gt;

        &lt;/Levels&gt;



    &lt;/ej:Treemap&gt;

    &lt;/div&gt;


{% endhighlight %}

 ![](TreeMap-Elements_images/TreeMap-Elements_img1.png)
{:.image }


## Header

You can set headers for each level by setting the ShowHeader propery of the each TreeMap levels. The HeaderHeight property helps to set the height of the header and Group path value determines the header value. You can customize the default header appearance by setting the HeaderTemplate of the TreeMap levels.





{% highlight html %}


[ASP]

[ASPX.CS]

  protected void Page_Load(object sender, EventArgs e)

        {

            this.treemap.DataSource = TreeMapPopulationData.GetData();



        }

 [ASPX]



&lt;div style="min-height:404px"&gt;

    &lt;ej:Treemap ID="treemap" runat="server" ColorValuePath = "Growth" WeightValuePath = "Population" ShowLegend = "true" &gt;

       &lt;TreeMapLegend IconHeight = "17" IconWidth = "17"&gt;&lt;/TreeMapLegend&gt;

        &lt;LeafItemSettings LabelPath = "Country"&gt;&lt;/LeafItemSettings&gt;



         &lt;TreeMapRangeColorMappings&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

        &lt;/TreeMapRangeColorMappings&gt;



        &lt;Levels&gt;

            &lt;ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25"&gt;&lt;/ej:TreeMapLevel&gt;

        &lt;/Levels&gt;



    &lt;/ej:Treemap&gt;

    &lt;/div&gt; 

{% endhighlight %}


 ![](TreeMap-Elements_images/TreeMap-Elements_img2.png) 
{:.image }


## Label

You can also set labels for the leaf nodes by setting the ShowLabels property as true. Group path value is displayed as a label for leaf nodes. You can customize the default label appearance by setting the LabelTemplate of the TreeMap levels.






{% highlight html %}

[ASP]

[ASPX.CS]

  protected void Page_Load(object sender, EventArgs e)

        {

            this.treemap.DataSource = TreeMapPopulationData.GetData();



        }



[ASPX]



&lt;div style="min-height:404px"&gt;

    &lt;ej:Treemap ID="treemap" runat="server" ColorValuePath = "Growth" WeightValuePath = "Population" ShowLegend = "true" &gt;

       &lt;TreeMapLegend IconHeight = "17" IconWidth = "17"&gt;&lt;/TreeMapLegend&gt;

        &lt;LeafItemSettings LabelPath = "Country"&gt;&lt;/LeafItemSettings&gt;



         &lt;TreeMapRangeColorMappings&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

        &lt;/TreeMapRangeColorMappings&gt;



        &lt;Levels&gt;

            &lt;ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25"&gt;&lt;/ej:TreeMapLevel&gt;

        &lt;/Levels&gt;



    &lt;/ej:Treemap&gt;

    &lt;/div&gt;

	
{% endhighlight %}


![](TreeMap-Elements_images/TreeMap-Elements_img3.png) 
{:.image }


