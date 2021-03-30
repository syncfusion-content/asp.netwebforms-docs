---
layout: post
title: TreeMap Elements | TreeMap | ASP.NET | Syncfusion
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

### Legend

You can set the color value of **leaf nodes** using `TreeMapLegend`. This legend is appropriate only for the TreeMap whose leaf nodes are colored using `RangeColorMapping`.

You can set `ShowLegend` property value to “true” to enable or disable legend visibility.

## TreeMap Legend

You can customize the treemap legend using following properties

* For customizing the alignment of legend, you can use `Alignment` property.

* You can set the legend column count using `ColumnCount` property.

* To set the dock position of the legend text, you can use `DockPosition`.

* You can specify the size of the legend by setting `Height` and `Width` of the `TreeMapLegend`.

* You can decide the size of the legend icons by setting `IconWidth` and `IconHeight` properties of the `TreeMapLegend` property avail in TreeMap.

* You can customize the left and right label text for the legend using `LeftLabel` and `RightLabel` properties.

* To set the legend mode as default or interactive, you can use `Mode` property.

* Using the property `Template`, you can specify template for legend settings.

* To set the legend title, you can use the `Title` property of the `LegendSettings`.

### Label for Legend

You can customize the labels of the legend item using `LegendLabel` property of `RangeColorMapping`. 

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

 ![ASPNET TreeMap TreeMap-Elements Image1](TreeMap-Elements_images/TreeMap-Elements_img1.png)

### Interactive Legend

The legends can be made interactive with an arrow mark indicating the exact range color in the legend when the mouse hovers over the corresponding treemap items. You can enable this option by setting `Mode` property in `Legend settings` value as “interactive” and default value of `Mode` property is “default” to enable the normal legend.

#### Title for Interactive Legend

You can provide the title for interactive legend by using `Title` property in `LegendSettings`.

#### Label for Interactive Legend

You can provide the left and right labels to interactive legend by using `LeftLabel` and `RightLabel` properties in `LegendSettings`. 

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" ShowLegend="true">
    <TreeMapLegend Mode="Interactive"
                LeftLabel ="20000000" 
                RightLabel="300000000" 
                Title = "Population"
                Height = "20" 
                Width = "150" 
                DockPosition = "Top" 
                Alignment="Center">
    </TreeMapLegend>
<ej:Treemap>

{% endhighlight %}

![ASPNET TreeMap TreeMap-Elements Image2](TreeMap-Elements_images/Interactive_Legend.png)

### Header

You can set headers for each level by setting the `ShowHeader` property of the each TreeMap levels. The `HeaderHeight` property helps to set the height of the header and Group path value determines the header value. You can customize the default header appearance by setting the `HeaderTemplate` of the TreeMap levels.

{% tabs %}
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
{% endtabs %}

 ![ASPNET TreeMap TreeMap-Elements Image3](TreeMap-Elements_images/TreeMap-Elements_img2.png) 

### Customizing the header

The text in the header can be customized by triggering the event `HeaderTemplateRendering` of the **TreeMap**. This event is triggered before rendering the header template. 

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" OnClientHeaderTemplateRendering="loadTemplate">
        <Levels>
            <ej:TreeMapLevel GroupPath = "Continent" ShowLabels = "true" GroupGap = "5" ShowHeader="false" LabelPosition="TopLeft" HeaderHeight = "25"></ej:TreeMapLevel>
        </Levels>
</ej:TreeMap>
	 <script  id="Template" type="application/jsrender">
        <div style="background-color: white; margin:5px">
            <label style="color:black;font-size:large;" >{{:header}}</label><br />            
        </div>                        
    </script> 

    <script type="text/javascript">
    function loadTemplate(sender) {
        //...                   
    }
    </script>

{% endhighlight %}


![ASPNET TreeMap TreeMap-Elements Image4](TreeMap-Elements_images/TreeMap-Elements_img4.png)

### Label

You can also set labels for the leaf nodes by setting the `ShowLabels` property as true. Group path value is displayed as a label for leaf nodes. You can customize the default label appearance by setting the LabelTemplate of the TreeMap levels.

{% tabs %}
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
{% endtabs %}

![ASPNET TreeMap TreeMap-Elements Image5](TreeMap-Elements_images/TreeMap-Elements_img3.png)

## Customizing the Overflow labels

You can handle the label overflow, by specifying any one of the following values to the property `TextOverflow`as

**None**       - It displays the default label text.
**Hide**       - You can hide the label, when it exceeds the header width.
**Wrap**       - You can wrap the label text by letter.
**WrapByWord** - You can wrap the label text by word.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server" OnClientHeaderTemplateRendering="loadTemplate">
        <LeafItemSettings ShowLabels = "true" TextOverflow="Wrap"></LeafItemSettings>
        <Levels>
            <ej:TreeMapLevel GroupPath = "Continent" HeaderTemplate="headertemplate" ShowLabels = "true" GroupGap = "5" ShowHeader="false" LabelPosition="TopLeft" HeaderHeight = "25"></ej:TreeMapLevel>
        </Levels>
</ej:TreeMap>
    <script  id="headertemplate" type="application/jsrender">
        <div style="background-color: white; margin:5px">
            <label style="color:black;font-size:medium;" >{{:header}}</label><br />            
        </div>                        
    </script>            

{% endhighlight %}

## Palette Color Mapping

Treemap is having support for `PaletteColorMapping`. You can set the color for palette color mapping using the property `Color` in palette color mapping.

{% highlight html %}

<ej:TreeMap ID="treemap" runat="server">
    <TreeMapPaletteColorMapping>
        //..
    </TreeMapPaletteColorMapping>
</ej:TreeMap>

{% endhighlight %}
