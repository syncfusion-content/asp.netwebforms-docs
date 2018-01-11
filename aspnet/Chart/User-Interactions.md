---
layout: post
title: Interactions available in Essential ASP.NET Chart
description: What are the interactions available in Chart like tooltip, crosshair, trackball, highlighting, zooming and panning, etc..,
platform: aspnet
control: Chart
documentation: ug
---

# User Interactions

## Tooltip

### Enable tooltip for data point

Tooltip for the data points can be enabled by using the *Visible* option of the **Tooltip** in the series.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series>
         <Tooltip Visible="true"></Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img1.png)

### Format the tooltip 

Tooltip displays data specified by the **Format** option of the tooltip. The default value of the format option is * **#point.x# : #point.y#** *. Here, * **#point.x#** * is the placeholder for x value of the point and * **#point.y#** * is the placeholder for y value of the point.

You can also use * **#series.<optionname>#** * as placeholder to display the value of an option in corresponding series and use * **#point.<optionname>#** * as place holder to display the value of an option in the corresponding point.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series>
           <%--Displaying tooltip in a format--%>
         <Tooltip Format="#series.name# <br/> #point.x# : #point.y#  (g/kWh)"></Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img2.png)


### Tooltip Template

HTML elements can be displayed in the tooltip by using the **Template** option of the tooltip. The template option takes the value of the id attribute of the HTML element. You can use the * **#point.x#** * and * **#point.y#** * as place holders in the HTML element to display the x and y values of the corresponding data point. 

You can also use * **#series.<optionname>#** * as place holder to display the value of an option in corresponding series of the tooltip and use * **#point.<optionname>#** * as place holder to display the value of an option in the corresponding point for which the tooltip is displayed.
  

{% highlight html %}


    <!-- Create Tooltip template here -->
    <div id="Tooltip" style="display: none;">
              <div id="icon"> <div id="eficon"> </div>  </div>
        <div id="value">
            <div>
               <label id="efpercentage">&nbsp;#point.y#% </label>
               <label id="ef">Efficiency </label>
            </div>
        </div>
    </div>

<ej:Chart ID="Chart1" runat="server" OnClientLoad="onchartload"> 
    <Series>
       <ej:Series>
           <%--Set template id to tooltip template--%>
         <Tooltip Template="Tooltip"></Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img3.png)

[Click](http://asp.syncfusion.com/demos/web/chart/defaultfunctionalities.aspx) here to view the Tooltip template online demo sample.


#### Tooltip template animation

You can enable animation by setting the *EnableAnimation* to true. Tooltip animates when the mouse moves from one data point to another point. The **Duration** property in tooltip specifies the time taken to animate the tooltip. the duration is set to **"500ms"**, by default.

N> Tooltip is animated only if the template is specified for tooltip.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series>
           <%--Change tooltip color and border--%>
         <Tooltip EnableAnimation="true" Duration="1000ms"></Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}


### Customize the appearance of tooltip   

The *Fill* and *Border* options are used to customize the background color and border of the tooltip respectively. The *Font* option in the tooltip is used to customize the font of the tooltip text.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series>
           <%--Enable tooltip template animation and set duration time--%>
         <Tooltip Fill="#FF9933">
             <Border Color="#993300" Width="1" />
         </Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img4.png)

#### Tooltip with rounded corners

The options *RX* and *RY* are used to customize the corner radius of the tooltip rectangle.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series>
           <%--Customize the corner radius of the tooltip rectangle--%>
         <Tooltip RX="50" RY="50">
         </Tooltip>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}


![](User-Interactions_images/User-Interactions_img5.png)

## Zooming and Panning

### Enable Zooming

There are two ways you can zoom the chart,

* When the **Zooming.Enable** option is set to true, you can zoom the chart by using the rubber band selection.

* When the **Zooming.EnableMouseWheel** option is set to true, you can zoom the chart on mouse wheel scrolling.

* When **Zooming.EnablePinching** option is set to *true*, you can zoom the chart through pinch gesture.

N> Pinch zooming is supported only in browsers that support multi-touch gestures. Currently IE10, IE11, Chrome and Opera browsers support multi-touch in desktop devices. 

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <%--Enable zooming in chart--%>
   <Zooming Enable="true" />
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img6.png)


After zooming the chart, a zooming toolbar will appear with options to *zoom*, *pan* and *reset*. Selecting the Pan option will allow to pan the chart and selecting the Reset option will reset the zoomed chart.

![](User-Interactions_images/User-Interactions_img7.png)

[Click](http://mvc.syncfusion.com/demos/web/chart/zoomingandpanning) here to view the Zooming and Panning online demo sample.


### Types of zooming

The *Type* option in zooming specifies whether the chart is allowed to scale along the horizontal axis(x) or vertical axis(y) or along both axis(xy). The default value of the Type is **xy** (both axis).

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <%--Enable horizontal zooming--%>
   <Zooming Enable="true" Type="x" />
</ej:Chart>

{% endhighlight %}


### Customizing zooming toolbar

The user can choose the items displayed in the zooming toolbar by specifying the property **ToolBarItems**.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">  
    <%-- Customizing zooming toolbar --%>        
      <Zooming Enable="true”>
         <ToolbarItems>
               <ej:ToolbarItems Text="reset" />
               <ej:ToolbarItems Text="zoomIn" />
               <ej:ToolbarItems Text="zoomOut" />
          </ToolbarItems>
      </Zooming>
</ej:Chart>  

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img8.png)

### Enable ScrollBar

Essential Chart provides scrollbar support to view the other portions of chart area which is not shown in the view port when zoomed, by setting true to **EnableScrollbar** property in **Zooming**.  

{% highlight html %}


<ej:Chart ID="Chart" runat="server">  
	<%-- Enable zooming scrollbar in Chart --%>        
    <Zooming Enable="true” EnableScrollbar="true">    
    </Zooming>
</ej:Chart>


{% endhighlight %}

![](User-Interactions_images/User-Interactions_img9.png)

## Crosshair

Crosshair is used to view the value of an axis at mouse position or touch contact point. 

### Enable Crosshair and Crosshair label

Crosshair can be enabled by using the **Visible** option in the Crosshair. Crosshair label for an axis can be enabled by using the Visible option of CrosshairLabel in the corresponding axis.


{% highlight html %}

<ej:Chart ID="Chart" runat="server">  
     <PrimaryXAxis>
    <%--Enable crosshairLabel to X-Axis--%>  
         <CrosshairLabel Visible="true"></CrosshairLabel>      
     </PrimaryXAxis>
     <PrimaryYAxis>
    <%--Enable crosshairLabel to Y-Axis--%>  
         <CrosshairLabel Visible="true"></CrosshairLabel>      
     </PrimaryYAxis>
     <%--Initializing Crosshair--%>
    <Crosshair Visible="true"></Crosshair>
</ej:Chart> 

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img10.png)


[Click](http://asp.syncfusion.com/demos/web/chart/crosshair.aspx) here to view the Crosshair online demo sample.


### Customize the Crosshair line and Crosshair label

The *Fill* and *Border* options of the **CrosshairLabel** is used to customize the background color and border of the crosshair label respectively. Color and width of the crosshair line can be customized by using the **Line** option in the Crosshair.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
     <PrimaryYAxis>
    <%--Customizing the crosshair label background color and border--%>  
         <CrosshairLabel Visible="true" Fill="red">
             <Border Color="green" Width="2" />
         </CrosshairLabel>      
     </PrimaryYAxis>
    <Crosshair Visible="true">
        <%--Customizing the crosshair line--%>
        <Line Color="grey" Width="2" />
    </Crosshair>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img11.png)


## Trackball

Trackball is used to track a data point close to the mouse position or touch contact point. Trackball marker indicates the closest point and trackball tooltip displays the information about the point.

### Enable Trackball

Trackball can be enabled by setting the *Visible* option of the crosshair to *true* and then set the **Type** as *Trackball*. The default value of type is *Crosshair*.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
    <%--Change crosshair type to trackball--%>
    <Crosshair Visible="true" Type="Trackball">
    </Crosshair>
</ej:Chart> 

{% endhighlight %}


![](User-Interactions_images/User-Interactions_img12.png)

[Click](http://asp.syncfusion.com/demos/web/chart/trackball.aspx) here to view the Trackball online demo sample.


#### Customize trackball marker and trackball line

Shape and size of the trackball marker can be customized by using the *Shape* and *Size* options of the Crosshair marker. Color and width of the trackball line can be customized by using the *Line* option in the crosshair.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
    <%--Initializing Crosshair--%>
    <Crosshair Visible="true" Type="Trackball">
        <%--Customize the trackball line color and width--%>
        <Line Color="#800000" Width="2" />
        <%--Customize the trackball marker shape size and visibility--%>
        <Marker Visible="true" Shape="Pentagon">
            <Size Width="9" Height="9" />
        </Marker>
    </Crosshair>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img13.png)


### Format Trackball tooltip

X and Y values displayed in the trackball tooltip are formatted based on its axis *LabelFormat*.  

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
    <%--Add format to crosshair label--%>
    <PrimaryXAxis LabelFormat="MMM, yyyy"></PrimaryXAxis>
    <PrimaryYAxis LabelFormat="{value}K"></PrimaryYAxis>
    <%--Initializing Crosshair--%>
    <Crosshair Visible="true" Type="Trackball">
    </Crosshair>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img14.png)


You can able to show the trackball tooltip in two modes, using trackballTooltipSettings.

                1.	Grouping.
                2.	Float. 

{% highlight javascript %}


<ej:Chart ID="Chart1" runat="server"> 
   //…
    <%--Enable crosshair and trackball mode --%>
       <Crosshair Visible="true" Type="trackball">
         <TrackballTooltipSettings Rx=”3” Ry=”3” Fill=”whitesmoke” Mode=”grouping”>
                 <Border Width=”1” Color=”grey”></Border>
         </TrackballTooltipSettings>
       </Crosshair>
   //..
</ej:Chart>


{% endhighlight %}

![](User-Interactions_images/User-Interactions_img30.png)


## Highlight

EjChart provides highlighting support for the series and data points on mouse hover. To enable the highlighting option, set the *Enable* property to *true* in the **HighlightSettings** of the series.

N> When hovering mouse on the data points, the corresponding series legend also will be highlighted.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--enable the highlight settings--%>
           <HighlightSettings Enable="true"></HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}

[Click](http://asp.syncfusion.com/demos/web/chart/selection.aspx) here to view the highlight and selections online demo sample.


### Highlight Mode

You can set three different highlight mode for the highlighting data point and series by using the **Mode** property of the *HighlightSettings*.

* Series
* Points
* Cluster

**Series mode**

To highlight all the data points of the specified series, you can set the **Series** value to the *Mode* option in the HighlightSettings. 


{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change highlight mode--%>
           <HighlightSettings Enable="true" Mode="Series"></HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img15.png)

**Point mode**

To highlight a single point, you can set the **Point** value to the *Mode* option.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change highlight mode--%>
           <HighlightSettings Enable="true" Mode="Point"></HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img16.png)


**Cluster mode**

To highlight the points that corresponds to the same index in all the series, set the **Cluster** value to the *Mode* option.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change highlight mode--%>
           <HighlightSettings Enable="true" Mode="Cluster"></HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img17.png)

### Customize the highlight styles

To customize the highlighted series, use the *Color*, *Border* and *Opacity* options in the HighlightSettings.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <HighlightSettings Opacity="0.5" Color="green">
               <%--Customizing styles--%>
               <Border Color="red" Width="1.5" />
           </HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img18.png)

### Patterns to highlight

EjChart provides pattern support for highlighting the data by setting the value to the **Pattern** property of the HighlightSettings. The different types of highlight patterns are as follows.

1.	Chessboard
2.	Crosshatch
3.	Dots
4.	Pacman
5.	Grid
6.	Turquoise
7.	Star
8.	Triangle
9.	Circle
10.	Tile
11.	HorizontalDash
12.	VerticalDash
13.	Rectangle
14.	Box
15.	VerticalStripe
16.	HorizontalStripe
17.	Bubble
18.	DiagonalBackward
19.	DiagonalForward

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change pattern--%>
           <HighlightSettings Pattern="Chessboard">
           </HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img19.png)


#### Custom pattern

To create a custom pattern for the highlighting data points, set the pattern type as **Custom** and add the custom pattern *Id* in the **CustomPattern** option of the HighlightSettings.

{% highlight html %}


            <svg>
                <pattern id="dots_a" patternUnits="userSpaceOnUse" width="6" height="6">
                    <rect x="0" y="0" width="6" height="6" transform="translate(0,0)" fill="black" opacity="1"></rect>
                    <path d='M 3 -3 L -3 3 M 0 6 L 6 0 M 9 3 L 3 9'stroke-width="1" stroke="white"></path>
                </pattern>
            </svg>

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Add custom pattern for highlighting data--%>
           <HighlightSettings Pattern="Custom" CustomPattern="dots_a">
           </HighlightSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}


## Selection

EjChart provides selection support for the series and data points on mouse click. To enable the selection option, set the *Enable* property to *true* in the SelectionSettings* of the series.

N> When mouse is clicked on the data points, the corresponding series legend also will be selected.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--enable the selection settings--%>
           <SelectionSettings Enable="true">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

[Click](http://asp.syncfusion.com/demos/web/chart/selection.aspx) here to view the highlight and selections online demo sample.


### Selection Mode

You can set four different selection mode for highlighting the data point and series by using the **Mode** property of the SelectionSettings.

* Series
* Points
* Cluster
* Range

**Series mode**

To select all the data points of the specified series, you can set the **Series** value to the *Mode* option in the SelectionSettings.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change selection mode--%>
           <SelectionSettings Mode="Series">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img20.png)

**Point mode**

To highlight a single point, you can set the **Point** value to the *Mode* option. 

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change selection mode--%>
           <SelectionSettings Mode="Point">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img21.png)


**Cluster mode**

To select the points that corresponds to the same index in all the series, set the **Cluster** value to the *Mode* option.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change selection mode--%>
           <SelectionSettings Mode="Cluster">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img22.png)

**Range mode**

To fetch the selected area data points value, you can set the **Mode** as **Range** in SelectionSettings. The selection rectangle can be drawn as horizontally, vertically or in both direction by using RangeType property and the selected data’s are returned as an array collection in the RangeSelected event.  

{% highlight html %}

<ej:Chart ID="Chart" RangeSelected = "rangeSelection" runat="server">
   <Series>
       <ej:Series>
           <%--Change selection mode--%>
           <SelectionSettings Enable="true" RangeType="XY" Mode="Range">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}
                            
                 
{% highlight js %}

	//event to fetch the selected data point values
    function rangeSelection(sender){
        var selectedData = sender.data.selectedDataCollection;
        //...
    }
	
{% endhighlight %}

![](User-Interactions_images/User-Interactions_img23.png)

[Click](http://asp.syncfusion.com/demos/web/chart/multipleselection.aspx) here to view the Multiple data selection online demo sample.

### Selection Type

You can set two different selection type for selecting the data point and series on mouse click by using the **Type** property of the SelectionSettings. 

* Single 
* Multiple 

**Single Type**

To select a data point or a series on mouse click based on the **SelectionSettings.Mode**, set **SelectionSettings.Type** as **Single** in the series.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <CommonSeriesOptions>
           <%--Selection mode is series and type --%>
           <SelectionSettings Mode="Series" Type="Single">
           </SelectionSettings>
   </CommonSeriesOptions>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img24.png)

**Multiple Type**

For selecting multiple data points or series on mouse click, set **SelectionSettings.Type** as **Multiple** in the series.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <CommonSeriesOptions>
           <%--Selection mode is series and type --%>
           <SelectionSettings Mode="Series" Type="Multiple">
           </SelectionSettings>
   </CommonSeriesOptions>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img25.png)


### Customizing selection styles

To customize the selection styles, use the *Color*, *Border* and *Opacity* options in the SelectionSettings.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Customizing selection rectangle styles--%>
           <SelectionSettings Opacity="0.5" Color="red">
               <Border Color="red" Width="1.5" />
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img26.png)


### Patterns for selection

EjChart provides pattern support for the data selection by setting the value to the **Pattern** property of the SelectionSettings. The different types of selection patterns are as follows.

1.	Chessboard
2.	Crosshatch
3.	Dots
4.	Pacman
5.	Grid
6.	Turquoise
7.	Star
8.	Triangle
9.	Circle
10.	Tile
11.	HorizontalDash
12.	VerticalDash
13.	Rectangle
14.	Box
15.	VerticalStripe
16.	HorizontalStripe
17.	Bubble
18.	DiagonalBackward
19.	DiagonalForward

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Change selection pattern--%>
           <SelectionSettings Pattern="DiagonalForward">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img27.png)


#### Custom pattern

To create a custom pattern for selecting the data points, set the *Pattern* type as **Custom** and add the custom pattern *id* in the **CustomPattern** option of the SelectionSettings.

{% highlight html %}

    <div id="container"></div>
            <svg>
                <pattern id="dots_a" patternUnits="userSpaceOnUse" width="6" height="6">
                    <rect x="0" y="0" width="6" height="6" transform="translate(0,0)" fill="black" opacity="1"></rect>
                    <path d='M 3 -3 L -3 3 M 0 6 L 6 0 M 9 3 L 3 9'stroke-width="1" stroke="white"></path>
                </pattern>
            </svg>
            

<ej:Chart ID="Chart" runat="server">
   <Series>
       <ej:Series>
           <%--Add custom pattern for selection data--%>
           <SelectionSettings Pattern="Custom" CustomPattern="dots_a">
           </SelectionSettings>
		</ej:Series>
   </Series>
</ej:Chart> 

{% endhighlight %}


![](User-Interactions_images/User-Interactions_img28.png)


### Handling Series Selection

To get the series information when selecting the specific series, subscribe to the **SeriesRegionClick** event and set the **SelectionSettings.Mode** as *Series*.

{% highlight html %}

    <%--Subscribe series selection event--%>
<ej:Chart ID="Chart" runat="server" OnClientSeriesRegionClick="seriesSelection">
   <Series>
       <ej:Series>
           <%--Change selection mode--%>
           <SelectionSettings Enable="true" Mode="Series">
           </SelectionSettings>
       </ej:Series>
   </Series>
</ej:Chart>

{% endhighlight %}

{% highlight js %}

        function seriesSelection(sender) {
            //Get Series information on series selection
            var seriesData = sender.series;
        }

{% endhighlight %}


### Selection on Load

We can able to select the point/series programmatically on chart load, by setting series and point index in the selectedDataPointIndexes property.

{% highlight javascript %}

<%--Added Selected Data point indexes--%>
<ej:Chart ID="Chart1" runat="server"> 
          //.... . . 
        <SelectedDataPointIndexes> 
                  <ej:SelectedDataPointIndexes SeriesIndex=”0”  PointIndex=”2” />
                  <ej:SelectedDataPointIndexes SeriesIndex=”1”  PointIndex=”4” />
         </SelectedDataPointIndexes> 
                //.... . . 
</ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img29.png)


## Data Editing

EjChart provides support to change the location of the rendered points. This can be done by dragging the point and dropping it on another location in chart. To enable the data editing, set the **enable** property to true in the **dragSettings** of the series.

{% highlight html %}

<ej:Chart ID="chartcontainer" runat="server">
        <CommonSeriesOptions>
                <DragSettings Enable="true" />
            </CommonSeriesOptions>
      </ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img31.png)

[Click](http://asp.syncfusion.com/demos/web/chart/dragdrop.aspx) here to view the data editing online demo sample.

### Customize Dragging direction

To drag the point along x and y axes, you can specify **type** as xy in **dragSettings**. And to drag along x axis alone, specify the type as x and to drag along y axis, specify type as y.

{% highlight html %}

<ej:Chart ID="chartcontainer" runat="server">
        <CommonSeriesOptions>
                <DragSettings Type="Y" />
            </CommonSeriesOptions>
      </ej:Chart>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img32.png)
