---
layout: post
title: Getting Started | TreeMap | ASP.NET | Syncfusion
description: getting started
platform: aspnet
control: TreeMap
documentation: ug
---

# Getting Started

This section explains briefly about how to create a TreeMap in your application with ASP.NET.

## Create your First TreeMap in ASP.NET

This section explains briefly on how to create a TreeMap in your application.

### Configure a TreeMap

You can configure ASP.NET TreeMap in simple steps. This manual provides instructions on how to configure TreeMap with grouping of populated datum based on population growth in population in each continent.  It also provides a walk-through on some of the customization feature available in TreeMap control.

![](Getting-Started_images/Getting-Started_img1.png)

### Create a simple ASP.NET Application

You can create a new ASP.NET project application by adding the necessary dll's and scripts.

#### Referencing Syncfusion Assemblies

The following assemblies need to be referenced in your application for using Essential Treemap ASP

1. Syncfusion.EJ.dll
2. Syncfusion.EJ.Web.dll

Follow the steps given below to deploy the application in the development server by referencing the assembly in **GAC**.

* Web.config file should be configured according to the referenced assemblies.
* To deploy your application, you have to ensure that the above referenced assemblies (in your web.config files) are present in the GAC.

![](Getting-Started_images/Getting-Started_img10.png)

And, add the Syncfusion namespace in the Web.config file.

![](Getting-Started_images/Getting-Started_img8.png)

N> If you are referring Syncfusion assemblies manually from bin folder to create ASP Treemap, then remove Culture, Version and PublicKeyToken attributes used in all files.

####  Adding script reference

By default, Syncfusion JavaScript source files has been included into the EJ.Web assembly as an embedded source. So we no need to refer jQuery and Syncfusion scripts externally. For debugging purpose want to refer script files externally, set false to **LoadEJResourcesFromAssembly** in Web.config file as shows in the below image and refer jQuery and Syncfusion script files.

![](Getting-Started_images/Getting-Started_img9.png)

{% highlight html %}


    <!--  jquery script  -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <!-- Essential JS UI widget -->
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>

{% endhighlight %}

N> If you are using the Essential Studio below 13.4.0.53 version, then you need to refer **jQuery.globalize.js** script file along with the above references to render the Treemap control.

#### Initialize Map

1.Add the following code in the default.aspx file to create the treemap control in View page.

{% highlight html %}

<ej:Treemap ID="Container" runat="server" >
</ej:Treemap>

{% endhighlight %}

#### Add Data

You can populate the TreeMap data inside the TreeMap .For example, you can populate data of few countries from the following location.

TreeMap/ TreeMap.aspx.cs

{% highlight C# %}

[Serializable]
public class TreeMapPopulationData

{

    public string Continent { get; set; }

    public string Country { get; set; }

    public int Growth { get; set; }

    public long Population { get; set; }



    public static List<TreeMapPopulationData> GetData()

    {

        List<TreeMapPopulationData> pop = new List<TreeMapPopulationData>();

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Indonesia", Growth = 3, Population = 237641326 });

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Russia", Growth = 2, Population = 152518015 });

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Mal", Growth = 1, Population = 29672000 });

        pop.Add(new TreeMapPopulationData() { Continent = " America", Country = "United States", Growth = 4, Population = 315645000 });

        pop.Add(new TreeMapPopulationData() { Continent = " America", Country = "Mexico", Growth = 2, Population = 112336538 });

        pop.Add(new TreeMapPopulationData() { Continent = " America", Country = "Canada", Growth = 1, Population = 39056064 });

        pop.Add(new TreeMapPopulationData() { Continent = " America", Country = "Colombia", Growth = 1, Population = 47000000 });

        pop.Add(new TreeMapPopulationData() { Continent = " America", Country = "Brazil", Growth = 3, Population = 193946886 });

        pop.Add(new TreeMapPopulationData() { Continent = "Africa", Country = "Nigeria", Growth = 2, Population = 170901000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Africa", Country = "Egypt", Growth = 1, Population = 83661000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "Germany", Growth = 1, Population = 81993000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "France", Growth = 1, Population = 65605000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "UK", Growth = 1, Population = 63181775 });

        return pop;

    }

}

{% endhighlight %}

N> Population data is referred from [List of continents by population](http://en.wikipedia.org/wiki/List_of_continents_by_population).

### Initialize TreeMap

1. Create an HTML file and add necessary script and CSS files in Head tag as illustrated in the following code example.

   ~~~ html

        <html xmlns="http://www.w3.org/1999/xhtml">

         <head>

            <title> Getting Started with Maps </title>

                    <!--  jquery script  -->

                    <script src="http://code.jquery.com/jquery-1.10.1.min.js" type="text/javascript"></script>



                    <!-- Essential JS UI widget -->

                   <script src="http://cdn.syncfusion.com/13.1.0.21/js/ej.widgets.all.min.js"></script>



                   <!-- JS Render widget -->

                   <script src="http://cdn.jsdelivr.net/jsrender/1.0pre35/jsrender.min.js" type="text/javascript"></script>



          </head>

          <body>
          </body>

       </html>

   ~~~


2. Create a &lt;div&gt; tag and set the height and width to determine the TreeMap size to be rendered in “TreeMap.aspx” file in body tag.

   ~~~ html

		<html>

			  <body>

					<div style="min-height:404px">

				    </div>


			  </body>

		</html>

   ~~~


3. Add the following code in “TreeMap.aspx” file to initialize the TreeMap.

   ~~~ html

		<html>

			  <body>

				 <div style="min-height:404px">



					 <ej:Treemap ID="treemap" runat="server">

						</ej:Treemap>



				  </div>


			  </body>

		</html>

   ~~~


4. Add the DataSource in “TreeMap.aspx.cs” as illustrated in the following code sample.

   ~~~ cs

		protected void Page_Load(object sender, EventArgs e)

        {



            this.treemap.DataSource = TreeMapPopulationData.GetData();

        }

   ~~~


### DataSource

The `DataSource` property accepts the collection values as input. For example, you can provide the list of objects as input.

#### Weight Value Path

You can calculate the size of the object using `WeightValuePath` of TreeMap.

1. Populate the TreeMap with using the above properties.

   ~~~ cs

	 protected void Page_Load(object sender, EventArgs e)

     {

         this.treemap.DataSource = TreeMapPopulationData.GetData();

     }

   ~~~



   ~~~ html

		<div style="min-height:404px">

		<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population">



		</ej:Treemap>

		</div>

   ~~~

The following image displays a TreeMap with default properties using the above code.

![](Getting-Started_images/Getting-Started_img3.png)


### GroupTreeMap Items using Levels

You can group TreeMap Items using `Levels` in TreeMap.

#### Group Path

You can use `GroupPath` property for every flat level of the TreeMap control. It is a path to a field on the source object that serves as the “Group” for the level specified. You can group the data based on the `GroupPath` in the TreeMap control. When the `GroupPath` is not specified, then the items are not grouped and the data is displayed in the order specified in the `DataSource`.

#### Group Gap

You can use `GroupGap` property to separate the items from every flat level and to differentiate the levels mentioned in the TreeMap control.

The following code sample explains how to group TreeMap Items using ‘Levels’.


{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

    this.treemap.DataSource = TreeMapPopulationData.GetData();

}

{% endhighlight %}

{% highlight html %}

<div style="min-height:404px">

    <ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population">

        <Levels>

               <ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25">

               </ej:TreeMapLevel>

        </Levels>

    </ej:Treemap>

</div>

{% endhighlight %}

The following screenshot displays grouping of TreeMapItems using Levels

![](Getting-Started_images/Getting-Started_img4.png)



### Customizing TreeMap Appearance by Range

You can differentiate the nodes based on its value and color ranges using `RangeColorMapping`. You can also define the color value range using From and To properties.

#### Color Value Path

The `ColorValuePath` of TreeMap is a path to a field on the source object. You can determine the color for the object using ColorValuePath of TreeMap.

The following code sample explains how to customize TreeMap Appearance by Range.

{% tabs %}
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

    this.treemap.DataSource = TreeMapPopulationData.GetData();

}

{% endhighlight %}

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth">

    <TreeMapRangeColorMappings>

             <ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"></ej:TreeMapRangeColorMapping>

    </TreeMapRangeColorMappings>

    <Levels>

       <ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25">

       </ej:TreeMapLevel>

    </Levels>

</ej:Treemap>

{% endhighlight  %}
{% endtabs %}

The following screenshot displays customized TreeMap Appearance by Range.

![](Getting-Started_images/Getting-Started_img5.png)


### Enable Tooltip

You can enable the tooltip by setting `ShowTooltip` to ‘true’. By default, it takes the property of the bound object that is referred in the `WeightValuePath` and displays its content when the corresponding node is hovered. You can customize the template for tooltip using `TooltipTemplate` property.

#### Leaf Item Settings

You can customize the Leaf level TreeMap items using `LeafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `LabelPath` when defined.

The following code sample displays how the tooltip is enabled.

{% tabs %}
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{
    this.treemap.DataSource = TreeMapPopulationData.GetData();
}

{% endhighlight %}

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth">

<LeafItemSettings LabelPath = "Country">

</LeafItemSettings>

<TreeMapRangeColorMappings>

             <ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"></ej:TreeMapRangeColorMapping>

             <ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"></ej:TreeMapRangeColorMapping>

</TreeMapRangeColorMappings>

<Levels>

       <ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25">



       </ej:TreeMapLevel>

</Levels>

</ej:Treemap>

{% endhighlight %}
{% endtabs %}

The following screenshot displays the TreeMap when the Tooltip is enabled.

![](Getting-Started_images/Getting-Started_img6.png)

TreeMap with tooltip option
{:.caption}

### Legend

You can set the color value of leaf nodes using TreeMap `LegendSettings`. This legend is appropriate only for the TreeMap whose leaf nodes are colored using `RangeColorMapping`.

You can set `ShowLegend` property value to ‘true’ to make a Legend visible.

#### Label for Legend

You can customize the labels of the legend item using LegendLabel property of RangeColorMapping.

The following code sample displays how to add labels for legend in a TreeMap.

{% tabs %}
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{
    this.treemap.DataSource = TreeMapPopulationData.GetData();
}

{% endhighlight %}

{% highlight html %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ShowLegend = "true">

    <LeafItemSettings LabelPath = "Country"></LeafItemSettings>

    <TreeMapLegend IconHeight = "17" IconWidth = "17"></TreeMapLegend>

    <TreeMapRangeColorMappings>

                 <ej:TreeMapRangeColorMapping Color = "#77D8D8" Legendlabel = "1% Growth" From = "0" To = "1"></ej:TreeMapRangeColorMapping>

                 <ej:TreeMapRangeColorMapping Color = "#AED960" Legendlabel = "2% Growth" From = "0" To = "2"></ej:TreeMapRangeColorMapping>

                 <ej:TreeMapRangeColorMapping Color = "#FFAF51" Legendlabel = "3% Growth" From = "0" To = "3"></ej:TreeMapRangeColorMapping>

                 <ej:TreeMapRangeColorMapping Color = "#F3D240" Legendlabel = "4% Growth" From = "0" To = "4"></ej:TreeMapRangeColorMapping>

    </TreeMapRangeColorMappings>

    <Levels>

           <ej:TreeMapLevel GroupPath = "Continent" GroupGap = "5" HeaderHeight = "25">

           </ej:TreeMapLevel>

    </Levels>

</ej:Treemap>

{% endhighlight %}
{% endtabs %}

The following screenshot displays the TreeMap when Legends are enabled.

![](Getting-Started_images/Getting-Started_img7.png)