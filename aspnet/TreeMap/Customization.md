---
layout: post
title: Customization | TreeMap | ASP.NET | Syncfusion
description: customization
platform: aspnet
control: TreeMap
documentation: ug
---

# Customization

TreeMap control supports color customization to determine the exact combination of colors for tree nodes displayed in TreeMap and tooltip support to display additional information of treemap data.

### Color Customization

You can customize the color of leaf nodes in **Treemap** either using ColorMapping support of the **Treemap** or mapping a field in the datasource.

## Binding color from the datasource

You can set color for each leaf items from data source by using `ColorPath` property. 

N> While setting color, do not set any other color mapping for treemap because color mapping has higher priority than `ColorPath` property. And also, if `ColorPath` is set, the legend will be generated for each leaf item in treemap. 

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" ColorPath="fill">

</ej:Treemap>

{% endhighlight %}

![](Customization_images/Customization_img5.png)


ColorMapping is categorized into three different types such as,

* `UniColorMapping`
* `RangeBrushColorMapping`
* `DesaturationColorMapping`

### UniColorMapping

You can color, all the leaf nodes with the same color by setting the `Color` value of the `UniColorMapping` property of the TreeMap.

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" >

        <TreeMapUniColorMapping Color = "#D73028"></TreeMapUniColorMapping>

</ej:Treemap>

{% endhighlight  %}

![](Customization_images/Customization_img1.png)

### Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the `To` and `From` values as range bound and `Color` or `GradientColors` values to fill the leaf nodes of the particular range, through the `RangeColorMapping` property of the **TreeMap**.

{% highlight html %}

<ej:Treemap ID="treemap" runat="server">

     <TreeMapRangeColorMappings>

         <ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"></ej:TreeMapRangeColorMapping>

         <ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"></ej:TreeMapRangeColorMapping>

         <ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"></ej:TreeMapRangeColorMapping>

         <ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"></ej:TreeMapRangeColorMapping>

    </TreeMapRangeColorMappings>

</ej:Treemap>


{% endhighlight  %}

![](Customization_images/Customization_img2.png) 

### Desaturation Color Mapping

You can differentiate all the leaf nodes using the `DesaturationColorMapping` property of the TreeMap. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using `RangeMinimum` and `RangeMaximum` value of the data collection. You can also bound the opacity range by setting `From` and `To` property of the `DesaturationColorMapping`.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server">

    <TreeMapDesaturationColorMapping From = "1" To ="0.5" Color="#41B8C4" RangeMinimum="2000" RangeMaximum = "8000">

    </TreeMapDesaturationColorMapping>

</ej:TreeMap>

{% endhighlight %}


![](Customization_images/Customization_img3.png)


### Tooltip

You can enable the tooltip support for the TreeMap by setting the `ShowTooltip` property to true. By default, it takes the property of the bound object that is referred to in the `GroupPath` and displays its content when the corresponding node is tapped. The `TooltipTemplate` is a HTML element that is used to expose the custom template for the tooltip.

### Leaf Item Setting

You can customize the **Leaf level TreeMap** items using `LeafItemsSetting`. In `LeftItemSetting` following customization options are available.

* You can specify the border color using `BorderBrush` property.

* For customizing border thickness, you can use `BorderThickness` property.

* To customize the gap between the leaf items, you can use `Gap` property.

* You can specify the label template for the leaf item using `ItemTemplate` property.

* The Label and tooltip values take the property of bound object that is referred in the `LabelPath` when defined.

* You can specify the position of the leaf labels using `LabelPosition` property.

* You can control the mode of label visibility of the labels using `LabelVisibilityMode` property.

* To show or hide the visibility of the leaf item labels you can use `ShowLabels` property.

* For specifying over flow action of left item labels you can use `TextOverflow` property.

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{

    this.treemap.DataSource = TreeMapPopulationData.GetData();
}

{% endhighlight %}

{% highlight html %}

<div style="min-height:404px">

    <ej:Treemap ID="treemap" runat="server" ColorValuePath = "Growth" WeightValuePath = "Population" ShowLegend = "true" >

       <TreeMapLegend IconHeight = "17" IconWidth = "17"></TreeMapLegend>

        <LeafItemSettings LabelPath = "Country"></LeafItemSettings>

        <TreeMapRangeColorMappings>

             <ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"></ej:TreeMapRangeColorMapping>

        </TreeMapRangeColorMappings>

        <Levels>

            <ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25"></ej:TreeMapLevel>

        </Levels>

    </ej:Treemap>

</div>
	
{% endhighlight %}

![](Customization_images/Customization_img4.png)

### Border Brush

You can able to customize the border color of the treemap using the property `BorderBrush`. 

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" BorderBrush="White">
</ej:TreeMap>

{% endhighlight %}

### Border Thickness

For customizing the border thickness of the treemap, you can use the `BorderThickness` property.

{% highlight html %}

 <ej:TreeMap ID="treemap" runat="server" BorderThickness="1">
 </ej:TreeMap>

{% endhighlight %}

## Dock Position

You can position the legend at top, bottom, left and right side of the treemap as per your requirement. For changing the position as per your requirement, you can use `DockPosition` property.

<ts name="ej.datavisualization.TreeMap.DockPosition"/>
Specifies the dockPosition for legend

<table class="params">
	<thead>
		<tr>
			<th>Name </th>			
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td class="name">top</td>			
			<td class="description">specifies the top position</td>
		</tr>
		<tr>
			<td class="name">bottom</td>			
			<td class="description">specifies the bottom position</td>
		</tr>
    <tr>
			<td class="name">right</td>			
			<td class="description">specifies the bottom position</td>
		</tr>
    <tr>
			<td class="name">left</td>			
			<td class="description">specifies the left position</td>
		</tr>
	</tbody>
</table>

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server">
    <TreeMapLegend DockPosition="Top"></TreeMapLegend>
</ej:TreeMap>

{% endhighlight %}

### Clicking and Dragging

You can select the single treemap element on click and drag. To click and drag treemap items, you have to enable the `DraggingOnSelection` property.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" DraggingOnSelection="false">
</ej:TreeMap>

{% endhighlight %}

For selecting the group element of treemap while clicking and dragging, you can use `DraggingGroupOnSelection` property.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" DraggingGroupOnSelection="false">
</ej:TreeMap>

{% endhighlight %}

### Fill with Gradient

You can customize that whether gradient color have to be applied for treemap or not. This can be customized using the property `EnableGradient`.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" EnableGradient="false">
</ej:TreeMap>

{% endhighlight %}

### Responsive Treemap

You can customize whether treemap have to be responsive or not while resizing the container. For making treemap responsive you can use `EnableResize` or `IsResponsive` property.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" EnableResize="true">
</ej:TreeMap>

{% endhighlight %}

### GroupColorMapping

You can customize the color of the each group using `GroupColorMapping` property. To use group color mapping, kindly specify `GroupID` and `RangeColorMapping` inside the `GroupColorMapping`. 

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server">
    <TreeMapGroupColorMapping> 
        // ..
    </TreeMapGroupColorMapping>
</ej:TreeMap>
  
{% endhighlight %}

### GroupSelectionMode

You can specifies the selection mode of the treemap using `GroupSelectionMode` property. You can set either group selection mode value as `Default` or  `Multiple`. 

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" GroupSelectionMode="Default">
</ej:TreeMap>

{% endhighlight %}

### Header

You can specify the header for the parent item using the property `Header`. This is applicable only for hierarchical data source. 

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" Header="Country">
</ej:TreeMap>

{% endhighlight %}

### Specifying HierarchicalDatasource

You can specify whether data source bound for the treemap is hierarchical or not using the property `IsHierarchicalDatasource`.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" IsHierarchicalDatasource="true">
</ej:TreeMap>

{% endhighlight %}

### Treemap Items

You can specify the treemap items which you want to display in the treemap using the property `TreeMapItems`.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server">
    <TreeMapItems>
        //..
    </TreeMapItems>
</ej:TreeMap>

{% endhighlight %}