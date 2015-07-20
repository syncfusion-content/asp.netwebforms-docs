---
layout: post
title: Customization
description: customization
platform: aspnet
control: TreeMap
documentation: ug
---

# Customization

TreeMap control supports color customization to determine the exact combination of colors for tree nodes displayed in TreeMap and tooltip support to display additional information of treemap data.

Color Customization

You can customize the colors of the leaf nodes of TreeMap using the ColorMapping support of the TreeMap. 

ColorMapping is categorized into three different types such as,

* UniColorMapping
* RangeBrushColorMapping
* DesaturationColorMapping

Uni Color Mapping

You can color, all the leaf nodes with the same color by setting the color value of the UniColorMapping property of the TreeMap.






{% highlight html %}

 [ASPX]

&lt;ej:Treemap ID="treemap" runat="server" &gt;

        &lt;TreeMapUniColorMapping Color = "#D73028"&gt;&lt;/TreeMapUniColorMapping&gt;

&lt;/ej:Treemap&gt;

{% endhighlight  %}


![](Customization_images/Customization_img1.png) 
{:.image }


Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the “to” and “from” values as range bound and “color” value to fill the leaf nodes of the particular range, through the RangeColorMapping property of the TreeMap.






{% highlight html %}

[ASP]

[ASPX]

&lt;ej:Treemap ID="treemap" runat="server"&gt;



         &lt;TreeMapRangeColorMappings&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

             &lt;ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"&gt;&lt;/ej:TreeMapRangeColorMapping&gt;

        &lt;/TreeMapRangeColorMappings&gt;

&lt;/ej:Treemap&gt;


{% endhighlight  %}

![](Customization_images/Customization_img2.png) 
{:.image }


Desaturation Color Mapping

You can differentiate all the leaf nodes using the DesaturationColorMapping property of the TreeMap. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using RangeMinimum and RangeMaximum value of the data collection. You can also bound the opacity range by setting from and to property of the DesaturationColorMapping.






{% highlight html %}

[ASP]

[ASPX]

&lt;ej:TreeMap ID="treemap" runat="server"&gt;

&lt;TreeMapDesaturationColorMapping From = "1" To ="0.5" Color="#41B8C4" RangeMinimum="2000" RangeMaximum = "8000"&gt;

        &lt;/TreeMapDesaturationColorMapping&gt;

&lt;/ej:TreeMap&gt;

{% endhighlight %}


![](Customization_images/Customization_img3.png)


Tooltip

You can enable the tooltip support for the TreeMap by setting the ShowTooltip property to true. By default, it takes the property of the bound object that is referred to in the GroupPath and displays its content when the corresponding node is tapped. The TooltipTemplate is a HTML element that is used to expose the custom template for the tooltip.

Leaf Item Setting

You can customize the Leaf level TreeMapitems using LeafItemsSetting. The Label and tooltip values take the property of bound object that is referred in the LabelPath when defined.




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

![](Customization_images/Customization_img4.png)


