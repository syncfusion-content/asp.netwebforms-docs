---
layout: post
title: Customization | Maps | ASP.NET Webforms | Syncfusion
description: customization
platform: aspnet
control: Maps
documentation: ug
---

# Customization

Maps control supports color customization to determine the exact combination of colors for shapes displayed in Maps and tooltip support to display additional information of shape data.

## Shapes Color Customization

The Map control highly supports the customization of the shape’s color. The shape’s color can be customized using the following ways:

1. Using the Fill, Stroke and StrokeThickness properties.
2. Color Mapping support.
3. Color Palette support.

## Shape Settings 

The ShapeSettings defines the basic customization settings of shapes in the map. 

The important property that makes an impact on shape colors is AutoFill. This AutoFill property is available in the ShapeSettings. 

* Fill - It is used to set the fill color of the shapes in the map.
* Stroke - It is used to set the border color of the shape in the map.
* StrokeThickness - It is used to set the border thickness of the shape in the map.
* HighlightColor - It is used to set the mouse hover color for shapes in the map.
* HighlightBorderWidth - It is used to set the mouse hover border width for shapes in the map.
* SelectionColor - It is used to set the selection color for shapes in the map.

The above properties of ShapeSettings are applied only when AutoFill property value is false. By map, AutoFill property value is false.



{% highlight html %}




  <ej:Map ID="map" runat="server">

        <Layers>

            <ej:ShapeLayer EnableMouseHover = "false" >

                <ShapeSettings Fill = "#9CBF4E" StrokeThickness = "0.5" Stroke = "White" HighlightColor = "#BC5353" ValuePath = "name" HighlightStroke = "White" AutoFill = "false"/>

            </ej:ShapeLayer>

        </Layers>

    </ej:Map> 



{% endhighlight %}



![ASPNET Map Customization Image1](Customization_images/Customization_img1.png)

_Map_

## Color Mapping

The Color Mapping support enables the customization of shape colors based on the underlying value of shape received from bounded data.

* ColorValuePath - It renders the field value that is to be fetched from data for each shape used for determining the shape color.
* ValuePath - It renders the field value that is to be fetched from data for each shape. This support also provides a tree map-like impact on the map UI. The various types of Color Mapping supported in maps are listed as follows.
* Range Color Mapping - It is used to differentiate the shape’s fill based on its underlying value and color ranges. 

The properties of Range color mapping are listed in the following table.

_Property Table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
From</td><td>
Double</td><td>
Gets or sets start value</td></tr>
<tr>
<td>
To</td><td>
Double</td><td>
Gets or sets end value</td></tr>
<tr>
<td>
Color</td><td>
Color</td><td>
Gets or sets the colors to be applied for specific range value containing shapes when enableGradient property value is false.</td></tr>
<tr>
<td>
Label</td><td>
String</td><td>
Gets or sets the label for legend when mode property value is ‘default’.</td></tr>
<tr>
<td>
GradientColors</td><td>
Array</td><td>
Gets or sets the start point and end point gradient colors to be applied for specific range value containing shapes when enableGradient property value is set to true.</td></tr>
</table>


{% highlight html %}



    <ej:Map ID="map" runat="server" >

        <Layers>

            <ej:ShapeLayer ShapeDataPath = "name" ShapePropertyPath = "name"  ShowMapItems = "false" >                

                <ShapeSettings Fill = "#9CBF4E" StrokeThickness = "0.1" Stroke = "white ValuePath = "population" EnableGradient = "true">

                </ShapeSettings>                    

            </ej:ShapeLayer>

        </Layers>        

    </ej:Map>   



{% endhighlight  %}
{% highlight c# %}

        protected void Page_Load(object sender, EventArgs e)

        {

(this.map.Layers[0] as ShapeLayer).ShapeSettings.ColorMappings = new ColorMapping() {

                MappingCollection = new List<object>()

                {

                    new RangeColorMapping() { From = 500000, To = 1000000, GradientColors = new List<string>() { "#9CBF4E", "#B8CE7B" } },

                    new RangeColorMapping() { From = 1000001, To = 5000000, GradientColors = new List<string>() { "#B8CE7B", "#CBD89A" } },

                    new RangeColorMapping() { From = 5000001, To = 10000000, GradientColors = new List<string>() { "#CBD89A", "#DEE2B9" } },

                    new RangeColorMapping() { From = 10000001, To = 40000000, GradientColors = new List<string>() { "#DEE2B9", "#F1ECD8" } }

                }

            };



        } 



{% endhighlight %}



When the underlying object value is 700000, then the fill color of the corresponding shape is set between #9CBF4E and #B8CE7B. 

When the underlying value is below any of the given sorted range or above the sorted range, then the Fill is set from Fill.



![ASPNET Map Customization Image2](Customization_images/Customization_img2.png)

_Map with fill_

* Equal Color Mapping - The Equal color mapping is used to differentiate the shape’s fill based on its underlying value and color. The properties of Equal color mapping is listed in the following table.

_Property table_

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
Value</td><td>
String</td><td>
Gets or sets the value.</td></tr>
<tr>
<td>
Color</td><td>
String</td><td>
Gets or sets the color for mapping.</td></tr>
</table>

In equal color mapping, value property contains the values of the field set in ColorValuePath property of shape settings.

Here “Map.aspx.cs” is populated with data of USA Election in “Map.aspx.cs” to provide election data as input datasource.



{% highlight html %}



    <ej:Map ID="map" runat="server">    



        <Layers>

            <ej:ShapeLayer ShapeDataPath = "State" ShapePropertyPath= "name">

                <ShapeSettings AutoFill = "false" Stroke = "white" ValuePath = "Electors" ColorValuePath = "Candidate>

                     <ColorMappings>

                             <MappingCollection>

                                 <ej:EqualColorMapping Value = "Romney" Color = "#D84444"></ej:EqualColorMapping>

                                 <ej:EqualColorMapping Value = "Obama" Color = "#316DB5"></ej:EqualColorMapping>

                             </MappingCollection>

                     </ColorMappings>

                </ShapeSettings>             

            </ej:ShapeLayer>

        </Layers>



    </ej:Map>



{% endhighlight %}

![ASPNET Map Customization Image3](Customization_images/Customization_img3.png)

_Map with fill color_

## Binding color from the datasource

By using `ColorPath` property, you can bind the specific field in the datasource to the map, and the shapes will be rendered based the color values available from the field you bind. 

N> While setting color for map by using `ColorPath` property, do not set any other color mapping hence color mapping is having higher priority than `ColorPath`. 


{% highlight html %}



    <ej:Map ID="map" runat="server">    



        <Layers>

            <ej:ShapeLayer ShapeDataPath = "State" ShapePropertyPath= "name">

                <ShapeSettings AutoFill = "false" Stroke = "white" ValuePath = "Electors" ColorPath = "shapeFill">
                     
                </ShapeSettings>             

            </ej:ShapeLayer>

        </Layers>



    </ej:Map>



{% endhighlight %}

![ASPNET Map Customization Image8](Customization_images/Customization_img8.png) 

While binding color path for map, it is possible to render legend for each shape in the map. To achieve this, set the `TextPath` for legend. `TextPath` contains another field name in the datasource. As per the text, content in the field legend will be generated. 


{% highlight html %}



    <ej:Map ID="map" runat="server">    



        <Layers>

            <ej:ShapeLayer ShapeDataPath = "State" ShapePropertyPath= "name">

                <ShapeSettings AutoFill = "false" Stroke = "white" ValuePath = "Electors" ColorPath = "shapeFill">
                     
                </ShapeSettings> 

                <LegendSettings showLegend = "true" Textpath = "fill">            
                
                </ej:LegendSettings>

            </ej:ShapeLayer>

        </Layers>



    </ej:Map>



{% endhighlight %}



![ASPNET Map Customization Image9](Customization_images/Customization_img9.png) 

            



## ColorPalette

When AutoFill property is set to true, shapes are filled with default colors from built-in palettes or custom palette.

## ColorPalette

The ColorPalette property determines whether the auto fill colors are fetched from built-in color palettes or custom palette.

The ColorPalette property can be set with Palette1, Palette2, Palette3 and CustomPalette values where Palette1, Palette2 and Palette3 are built-in color palettes and default value for this property is “Palette1”.



{% highlight html %}





       <ej:Map ID="map" runat="server" >    



         <Layers>

            <ej:ShapeLayer ShapeDataPath = "Name" ShapePropertyPath= "name" >

               <ShapeSettings StrokeThickness="0.5" Stroke = "white" AutoFill="true" />

            </ej:ShapeLayer>

        </Layers>

    </ej:Map> 



{% endhighlight %}



![ASPNET Map Customization Image4](Customization_images/Customization_img4.png) 

_Map with color palette property_


## CustomPalette

The CustomPalette property is used to set an array of colors to be auto filled in shapes.

This property is enabled only when ColorPalette property value is set to “CustomPalette”.



{% highlight c# %}



protected void Page_Load(object sender, EventArgs e)

        {

            (this.map.Layers[0] as ShapeLayer).DataSource = Election_Result.GetUSPopulationData();

            (this.map.Layers[0] as ShapeLayer).ShapeData = this.GetUSA();

            (this.map.Layers[0] as ShapeLayer).ShapeSettings = new ShapeSettings()

            {



                ColorPalette = ColorPalette.CustomPalette,

                CustomPalette= new List<string>(){

                          "#E51400", "#A4C400", "#730202",

                          "#008B00", "#EF6535",

                          "#1BA0E2", "#C63477", "#0050EF",

                          "#BF004D", "#AA00FF"}; 



            }



        } 



{% endhighlight %}



![ASPNET Map Customization Image5](Customization_images/Customization_img5.png)

_Map with custom palette_

## Tooltip

The tooltip is displayed only when you set ShowTooltip to “true” in the shape layers. By default, it takes the property of the bound object that is referred in the ValuePath and displays its content on hovering the corresponding shape. 



{% highlight html %}


    <ej:Map  ID =“map” runat =“server” >



         <Layers>

            <ej:ShapeLayer ShowTooltip="true" LayerType="Geometry" ShapeDataPath="name" ShapePropertyPath="name">

            // …

         <Layers>

    </ ej:Map > 



{% endhighlight %}



![ASPNET Map Customization Image6](Customization_images/Customization_img6.png)

_Map with Tooltip_

## Tooltip Template

The TooltipTemplate property is used for customizing the template for tooltip.



{% highlight html %}


   <ej:Map ID="map" runat="server" >    

         <Layers>

            <ej:ShapeLayer ShowTooltip="true" TooltipTemplate="template">

            </ej:ShapeLayer>

        </Layers>



    </ej:Map>



       <script  id="template" type="application/jsrender">



             <div  style="margin-left:17px;margin-top:-45px;">             

<div class="tip">

                             <p class="small" style="margin-top:8px">

                                    <label  style="color:white;font-size:14px;font-weight:normal;">{{:name}}</label>

                             </p>

                             <p class="big">

                                    <label style="color:white;font-size:11px;font-weight:normal;">Population : {{:~parseDouble(population)}}</label>

                             </p>

				    </div> 

               </div>               

        </script>



{% endhighlight %}



The following screenshot illustrates a map control displaying a Tooltip with template.


![ASPNET Map Customization Image7](Customization_images/Customization_img7.png)

_Map with tooltip template_


### Customize map background

The Map background can be customized by using the `Background` property of the Map. 


{% highlight html %}


    <ej:Map  ID =“map” runat =“server” Background="skyblue">


    </ ej:Map > 



{% endhighlight %}




### Base Map Index 

Specifies the index of the map to determine the shape layer to be displayed, you can use `BaseMapIndex` property and the default value is 0.


{% highlight html %}


    <ej:Map  ID =“map” runat =“server” BaseMapIndex="0">


    </ ej:Map > 



{% endhighlight %}



### Center Position 


Specify the `centerPosition` where map should be displayed


{% highlight html %}


    <ej:Map  ID =“map” runat =“server” BaseMapIndex="0" centerPosition= "">


    </ ej:Map > 



{% endhighlight %}


### Label Settings

The `labelSettings` defines the basic customization settings of labels in the map. 

The below properties are used for `labelSettings`

* `enableSmartLabel` - enable or disable the enableSmartLabel property.
* `labelLength` - set the labelLength property.
* `labelPath` - set the labelPath property.
* `showLabels` - The property specifies whether to show labels or not
* `smartLabelSize` - set the smartLabelSize property.



{% highlight html %}


    <ej:Map  ID =“map” runat =“server” BaseMapIndex="0" centerPosition= "">


    <Layers>

            <ej:ShapeLayer ShowTooltip="true" TooltipTemplate="template">

             <LabelSettings ShowLabels = "true" LabelPath = "iso_3166_2" EnableSmartLabel = "true"></LabelSettings>

            </ej:ShapeLayer>

    </Layers>


    </ ej:Map > 



{% endhighlight %}


