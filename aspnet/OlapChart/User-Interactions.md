---
layout: post
title: User-Interactions
description: user interactions
platform: aspnet
control: OLAP Chart
documentation: ug
---

#User Interactions

##Tooltip

###Enable Tooltip for Data Points
Tooltip for the data points can be enabled using the **"visible"** option of the `Tooltip` property under **"commonSeriesOptions"** of the OlapChart.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Enabling tooltip of data point
    <CommonSeriesOptions Tooltip-Visible="True" />
</ej:OlapChart>

{% endhighlight %}

![](User-Interactions_images/tooltip.png) 

###Tooltip Template
HTML elements can be displayed inside the tooltip by using the `Template` option. The template option takes the value of the "id" attribute from the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the X and Y values of the corresponding data points.

{% highlight html %}

<div id="Tooltip" style="display: none;">
    <div id="icon">
        <div id="ccicon"> </div>
    </div>
    <div id="value">
        <div>
            <label id="ccvalue">&nbsp;#point.y# </label>
            <label id="cc">Customer Count </label>
        </div>
    </div>
</div>
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Enabling tooltip of data point
    <CommonSeriesOptions Tooltip-Visible="True" Tooltip-Template="Tooltip" />
</ej:OlapChart>

{% endhighlight %}

![](User-Interactions_images/tooltiptemplate.png) 

###Tooltip Customization
By using `Fill` and `Border` properties of tooltip, you can customize its background color, border color and border width.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Change tooltip color and border
    <CommonSeriesOptions Tooltip-Visible="True" Tooltip-Fill="#FF9933" Tooltip-Border-Width="1" Tooltip-Border-Color="#993300" />
</ej:OlapChart>

{% endhighlight %}   

![](User-Interactions_images/tooltipcustomization.png) 

###Tooltip with Rounded Corners
The tooltip properties, `rx` and `ry` are used to customize its corner radius.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Customize the corner radius of the tooltip rectangle.
    <CommonSeriesOptions Tooltip-Visible="True" Tooltip-RX="50" Tooltip-RY="50" />
</ej:OlapChart>

{% endhighlight %} 

![](User-Interactions_images/tooltiprouded.png) 

##Zooming and Panning

###Enable Zooming

There are two ways to zoom the Chart:
* When `Zooming.Enable` option is set to true, you can zoom the Chart by using rubber band selection.
* When `Zooming.EnableMouseWheel` option is set to true, you can zoom the Chart on mouse wheel scrolling.

{% highlight html %}

//Enable zooming in chart
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Zooming-Enable="true" ClientIDMode="Static">
</ej:OlapChart>

{% endhighlight %} 

![](User-Interactions_images/zooming.png) 

After zooming the Chart, a zooming toolbar will appear with options to zoom, pan and reset. Selecting the **“Pan”** option will allow to view the Chart and selecting the **“Reset”** option will reset the zoomed Chart.

![](User-Interactions_images/pan.png) 

###Types of Zooming
You can zoom the particular axis like horizontal axis or vertical axis or both axis using `type` option in zooming. The default value is “x,y” (indicating both axis).

{% highlight html %}

//Enable horizontal zooming 
<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" Zooming-Enable="true" Zooming-Type="x" ClientIDMode="Static">
</ej:OlapChart>

{% endhighlight %}

##Marker and Crosshair

###Marker Shape Customization
In OlapChart, you can customize the marker `Shape` with different symbols like rectangle, circle, cross, diamond, pentagon, hexagon, star, ellipse, triangle etc.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Line" />
        <ClientSideEvents Load="loadTheme" SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)
                this.model.series[seriescount].marker.shape = "Triangle";
        }
    </script>
</body>

</html>                                           

{% endhighlight %}

![](User-Interactions_images/marker.png) 

###Enable Crosshair and Crosshair Label
Crosshair helps you to view the value at mouse position or touch contact point. Crosshair can be enabled by using the `Visible` option in `Crosshair` property. Crosshair label can be enabled by using the **“visible”** option in `CrosshairLabel` property within its corresponding axis.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Initializing Crosshair
    <CrossHair Visible="true"></CrossHair>
    //Enable crosshairLabel to X-Axis
    <PrimaryXAxis CrosshairLabel-Visible="true"></PrimaryXAxis>
    //Enable crosshairLabel to Y-Axis
    <PrimaryYAxis CrosshairLabel-Visible="true"></PrimaryYAxis>
</ej:OlapChart>

{% endhighlight %}

![](User-Interactions_images/crosshair.png) 

###Crosshair Line and Label Customization
By using `Line` property of crosshair, you can customize its line color and width. Also by using `Fill` and `Border` properties of crosshair label, you can customize its background color, border color and border width.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Customizing the crosshair line
    <CrossHair Visible="true" Line-Width="2" Line-Color="Gray"></CrossHair>
    //Customizing the crosshair label background color and border
    <PrimaryXAxis CrosshairLabel-Visible="true" CrosshairLabel-Fill="Red" CrosshairLabel-Border-Color="Green" CrosshairLabel-Border-Width="2">
    </PrimaryXAxis>
</ej:OlapChart>

{% endhighlight %}

![](User-Interactions_images/crosshairline.png) 

##Trackball

###Enable trackball
Trackball can be enabled by setting both - 'visible' option of the crosshair to true and `Type` option of the crosshair to **“trackball”.** The default value of type is **“crosshair”.**

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Change crosshair type to track ball
    <CrossHair Visible="true" Type="TrackBall"></CrossHair>
</ej:OlapChart>

{% endhighlight %}

![](User-Interactions_images/trackball.png) 

###Trackball Marker and Line Customization
Shape and size of the trackball marker can be customized using the `Shape` and `Size` options of the crosshair marker. Color and width of the trackball line can be customized using the **“line”** option in the crosshair.

{% highlight html %}

<ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
    //Customize the trackball line color and width, marker shape and visibility
    <CrossHair Visible="true" Line-Width="2" Line-Color="Gray" Type="TrackBall" Marker-Shape="Pentagon" Marker-Visible="true"></CrossHair>
</ej:OlapChart>

{% endhighlight %} 

![](User-Interactions_images/trackballmarker.png) 

##Highlight
OlapChart provides highlighting support for the series and data points on mouse hover. To enable highlighting, set the **“enable”** property to true in the `highlightsettings` option of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++)
                this.model.series[seriescount].highlightSettings.enable = true
        }
    </script>
</body>

</html>                                           

{% endhighlight %} 

###Highlight Mode
You can set three different modes for highlighting data points and series by using the `mode` property of the `highlightsettings`.
 
* series
* points
* cluster

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.mode = "series";
            }
        }
    </script>
</body>

</html>                                           

{% endhighlight %} 

![](User-Interactions_images/highlightmode.png) 

###Customize the Highlight Styles
To customize the highlighted series, use `border.color`, `border.width` and `opacity`
 options in the `highlightSettings` property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.opacity = "0.5";
                this.model.series[seriescount].highlightSettings.border.width = "1.5";
                this.model.series[seriescount].highlightSettings.border.color = "red";
            }
        }
    </script>
</body>

</html>                                            

{% endhighlight %} 

![](User-Interactions_images/customizehighlight.png) 

###Patterns to Highlight
OlapChart provides pattern support for highlighting the data by setting an appropriate value to the `pattern` property of the `highlightSettings`. The different types of highlight patterns are as follows.

* chessboard
* crosshatch
* dots
* packman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].highlightSettings.enable = true
                this.model.series[seriescount].highlightSettings.pattern = "chessboard";
            }
        }
    </script>
</body>

</html>                                            

{% endhighlight %} 

![](User-Interactions_images/patternhighlight.png) 

##Selection
OlapChart provides selection support for the series and data points on mouse click. To enable selection, set the **“enable”** property to true in the `selectionSettings` option of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
            }
        }
    </script>
</body>

</html>                                           

{% endhighlight %}

###Selection Mode

You can set three different selection mode for highlighting the data points and series by using the `mode` property of the `selectionSettings`.

* series
* points
* cluster

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
                this.model.series[seriescount].selectionSettings.mode = "series";
            }
        }
    </script>
</body>

</html>                                           

{% endhighlight %}

![](User-Interactions_images/selectionmode.png) 

###Customize the Selection Styles
To customize the selection styles, use the `border.color`, `border.width` and `opacity` options in the `selectionSettings`.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true;
                this.model.series[seriescount].selectionSettings.border.width = "1.5";
                this.model.series[seriescount].selectionSettings.border.color = "red";
            }
        }
    </script>
</body>

</html>                                          

{% endhighlight %}

![](User-Interactions_images/customizeselection.png) 

###Patterns for Selection
OlapChart provides pattern support for the selecting the data by setting an appropriate value to the `pattern` property of the `selectionSettings` option. The different types of selection patterns are as follows.

* chessboard
* crosshatch
* dots
* packman
* grid
* turquoise
* star
* triangle
* circle
* tile
* horizontalDash
* verticalDash
* rectangle
* box
* verticalStripe
* horizontalStripe
* bubble
* diagonalBackward
* diagonalForward

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml">
//...

<body>
    <ej:OlapChart ID="OlapChart1" runat="server" Url="../wcf/OlapChartService.svc" ClientIDMode="Static">
        <CommonSeriesOptions Type="Column" />
        <ClientSideEvents SeriesRendering="onSeriesRenders" />
    </ej:OlapChart>
    <script type="text/javascript">
        function onSeriesRenders(args) {
            for (var seriescount = 0; seriescount < this.model.series.length; seriescount++) {
                this.model.series[seriescount].selectionSettings.enable = true
                this.model.series[seriescount].selectionSettings.pattern = "chessboard";
            }
        }
    </script>
</body>

</html>                                           

{% endhighlight %}

![](User-Interactions_images/patternselecion.png) 
