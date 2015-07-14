---
layout: post
title: User-Interactions
description: user interactions
platform: aspnet
control: Chart
documentation: ug
---

## User Interactions

When you deal with a large amount of data, you require interactions like Tooltip, Crosshair etc that allows you to track data changes and provide interaction capabilities.  

### ToolTip

Essential Chart provides you an option tooltip to display a pop up with the point values, on mouse move over the appropriate point. Essential Chart also allows you to customize its border color, border width, opacity, fill color, animation, duration, rx, ry, font size, font family, font style, font color, font weight, etc. You can change the tooltip properties for each series in Chart to change its appearance. When you require the same tooltip for all the series in Chart, you can specify the Tooltip in CommonSeriesOptions. You can also modify the default template for the tooltip using Template property.

Tooltip visibility: 

By default the visibility of Tooltip is set to false, but you can change the visibility. When format or template is not specified for Tooltip, then it displays the x and y values of the point. 

[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server"&gt;       

         &lt;CommonSeriesOptions Tooltip-Visible="true"/&gt;

&lt;/ej:Chart&gt;





{ ![](User-Interactions_images/User-Interactions_img1.png) | markdownify }
{:.image }


Tooltip format: 

Essential Chart provides you support to change the format of the text displayed in the tooltip that allows you to use the data point information in desired format.

For single y value, Chart like line series, you can form a format as follows.

format: " #point.x##series.name#  #point.y#%"

For multiple y values, in financial series, you can form a format as follows.

format: " #point.x# #series.name# #point.high# #point.low# #point.open# #point.close# %"



[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server"&gt;       

      &lt;CommonSeriesOptions Tooltip-Visible="true" Tooltip-Format="In #point.x# #series.name# produced #point.y#%"/&gt;

     &lt;/ej:Chart&gt;





{ ![](User-Interactions_images/User-Interactions_img2.png) | markdownify }
{:.image }


Customize the tooltip border: 

Essential Chart provides you options to customize the Border of the Tooltip. You can change the width and color of the Border. By default the border width is set to 1.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server"&gt;   

&lt;CommonSeriesOptions Tooltip-Visible="true" Tooltip-Border-Width="1" Tooltip-Border-Color="#000000"/&gt;    

&lt;/ej:Chart&gt;





{ ![](User-Interactions_images/User-Interactions_img3.png) | markdownify }
{:.image }


Changing the tooltip fill color: 

You can modify the Fill color of Tooltip. By default the Tooltip renders with the appropriate series color as background color.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server"&gt;   

&lt;CommonSeriesOptions Tooltip-Visible="true" Tooltip-Fill="#000000"/&gt;

&lt;/ej:Chart&gt;





{ ![](User-Interactions_images/User-Interactions_img4.png) | markdownify }
{:.image }


Customize the tooltip font: 

Essential Chart provides you support to customize the text display in the Tooltip. You can change font family, font color, font style, font weight. By default “Segoe UI” font family is set to tooltip text.



[ASP.NET] 

&lt;ej:Chart ID="Chart" runat="server"&gt;       

         <CommonSeriesOptions Tooltip-Visible="true" Tooltip-Fill="#000000"   

            Tooltip-Font-FontStyle="Italic" Tooltip-Font-FontWeight="Lighter"  

            Tooltip-Font-FontSize="14px" Tooltip-Font-Color="#000000"/>

 &lt;/ej:Chart&gt;





{ ![](User-Interactions_images/User-Interactions_img5.png) | markdownify }
{:.image }


Tooltip Animation

Essential Chart provides you animation support for tooltip template. You can enable this by setting “EnableAnimation” to true. The “Duration” property in tooltip specificies the time taken to animate the tooltip, by default the duration is set to “500ms”.



[ASP.NET] 

&lt;ej:Chart ID="Chart" runat="server"&gt;       

   <CommonSeriesOptions Tooltip-Visible="true" Tooltip-Template="Tooltip"   

    Tooltip-EnableAnimation="true"/>

  &lt;/ej:Chart&gt;



Understanding the RX and RY in tooltip:

Essential Chart has RX and RY property in Tooltip to customize the corners radius of the tooltip.

[ASP.NET] 

&lt;ej:Chart ID="Chart" runat="server"&gt;       

   &lt;CommonSeriesOptions Tooltip-Visible="true" Tooltip-RX="50" Tooltip-RY="50"/&gt;

 &lt;/ej:Chart&gt;



{ ![](User-Interactions_images/User-Interactions_img6.png) | markdownify }
{:.image }


### Zooming and Panning

Essential Chart provides you an option to zoom the Chart. Using this option you can clearly view the points and data in Chart. Zooming is done by dragging the mouse on the Chart or by scrolling the mouse wheel. During runtime, you can simply select the range you want to zoom with the mouse and the Chart zooms-in accordingly.

Enable zooming: 

By default zooming is not enabled. You can enable it using the “Enable” option in “zooming” property.



[ASP.NET] 

&lt;ej:Chart ID="Chart1"&gt;

        &lt;Zooming Enable="true" /&gt;

 &lt;/ej:Chart&gt;





Before zooming:



{ ![](User-Interactions_images/User-Interactions_img7.png) | markdownify }
{:.image }


Selection for zooming:



{ ![](User-Interactions_images/User-Interactions_img8.png) | markdownify }
{:.image }


After zooming:



{ ![](User-Interactions_images/User-Interactions_img9.png) | markdownify }
{:.image }


Programmatic Zooming

Programmatically the Chart can be zoomed using ZoomPosition and ZoomFactor properties.Both the properties are usually between 0 and 1. When you set the zoomFactor to 1, the Chart isn't zoomed. When you set it to 0.5, the Chart is double its usual size. The ZoomPosition is used to set the starting position of the zoomed axis. For example, when both the properties are set to 0.5 for horizontal axis then the Chart is zoomed to double its size and the view port of the horizontal axis start from half of the axis. 

Enable zoom via mouse wheel: 

Essential Chart provides you support to zoom the Chart by scrolling the mouse wheel. By default it is not enabled, you can enable it with the EnableMouseWheel property in zooming.



[ASP.NET] 

&lt;ej:Chart ID="Chart1"&gt;

        &lt;Zooming Enable="true" EnableMouseWheel="true" /&gt;

 &lt;/ej:Chart&gt;

Types of zooming: 

Essential Chart supports three types of zooming. You can zoom only the x axis or can zoom only the y axis or can zoom both x and y axis respectively. This is achieved using Type property in zooming.



[ASP.NET] 

&lt;ej:Chart ID="Chart1"&gt;

        &lt;Zooming Enable="true" EnableMouseWheel="true" Type="y" /&gt;

 &lt;/ej:Chart&gt;



{ ![](User-Interactions_images/User-Interactions_img10.png) | markdownify }
{:.image }


### Crosshair and Trackball

To enable tracking of data points in a Chart, you can use Crosshair and Trackball.

Crosshair:

In order to view the value at mouse position or touch contact point, you can use the Crosshair property. You can customize the appearance further using the Crosshair.Line properties. 

To display the label containing the relevant data point value information, enable the CrosshairLabel.Visible property in the corresponding axis of the Chart. For example, to display the x-axis label you can set the Visible property in CrosshairLabel of the PrimaryAxis to true. You can customize labels and tooltip rect using font, fill and border properties in CrosshairLabel.

The following code example illustrates you on how to enable the Crosshair. 

[ASP.NET] 

&lt;ej:Chart ID="Chart1"&gt;

        &lt;PrimaryXAxis CrosshairLabel-Visible="true"&gt;&lt;/PrimaryXAxis&gt;

        &lt;PrimaryYAxis CrosshairLabel-Visible="true"&gt;&lt;/PrimaryYAxis&gt;

        &lt;CrossHair Visible="true" Type="Crosshair" Line-Width="2" Line-Color="Black" /&gt; &lt;/ej:Chart&gt;



{ ![](User-Interactions_images/User-Interactions_img11.png) | markdownify }
{:.image }


Trackball:

In order to track a data point closer to the mouse position or touch contact point, you can use trackball. You can customize the track ball appearance using the Marker and Line property in the crosshair. To display a label containing the relevant data point value information, you can enable the CrosshairLabel.Visible property in the corresponding axis of the Chart. For example, to display the x-axis label, set the Visible property of CrosshairLabel inthe PrimaryAxis to true. 

[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true"&gt;

  <PrimaryXAxis CrosshairLabel-Visible="true"    

                   CrosshairLabel-Fill="#E94649">&lt;/PrimaryXAxis&gt;        

        &lt;CrossHair Visible="true" Type="Trackball" Line-Width="2" Line-Color="Blue" /&gt;

      &lt;/ej:Chart&gt;



{ ![](User-Interactions_images/User-Interactions_img12.png) | markdownify }
{:.image }


### Drill Down

Drill Down allows you to view the data’s in depth, for example yearly data to quarterly, quarterly to monthly or from categorical data to individual item. The drill down support is achieved using the PointRegionClick event. On clicking points in Chart series, PointRegionClick event gets triggered, using this event you can refresh your Chart by assigning new data to the Chart series through set model. In the following example a pie Chart with two points are used, when you click on the pie slice, PointRegionClick event gets triggered. Using this event and set model option, the Chart is refreshed with new data based on the point index.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientPointRegionClick="onclick" OnClientAnimationComplete="completeAnimation"&gt;

     &lt;Series&gt;

         &lt;ej:Series Name="Market" Explode="True" XName="Xvalue" YName="YValue1" Type="Pie"&gt; 

                &lt;Points&gt;

                    &lt;ej:Points X="SUV" Y="25" Text="25%"/&gt;

                    &lt;ej:Points X="Car" Y="37" Text="37%"/&gt;

                    &lt;ej:Points X="Pickup" Y="15" Text="15%"/&gt;

                    &lt;ej:Points X="Minivan" Y="23" Text="23%"/&gt;

                &lt;/Points&gt;

            &lt;/ej:Series&gt;

    &lt;/ej:Chart&gt;



 [JS]

&lt;script&gt;

        function onclick(sender) {

            var pointIndex = sender.data.region.Region.PointIndex;

            if (sender.model.series[0].name == "Market")

                $("#Chart1").ejChart("option", { "drilldown": pieSeries(pointIndex) });

        }



        function pieSeries(index) {

            if (index == 0) {

                return {

                    title :{text: 'Automobile Sales in the SUV segment'},

                    series: [{

                        points: [ { x: "Toyota", y: 8, text:'Toyota 8%'}, 

                                  { x: "Ford", y: 12, text:'Ford 12%' }, 

                                 { x: "GM", y: 17, text:'GM 17%' }, 

                        ],



                        name: 'SUV-Sale', labelPosition: 'outside', enableAnimation : true,

                        marker: { 

                            dataLabel:{ visible:true, connectorLine :{height :40}, font: {  size: '12px', color: "#707070"  } }						

                        }

                    }],



                    legend: { visible: false }

                };

            }

            else if (index == 1) {

                return {

                    title :{text: 'Automobile Sales in the Car segment'},

                    series: [{

                        points: [{ x: "Toyota", y: 7, text:'Toyota 7%' }, 

                                 { x: "Chrysler", y: 12, text:'Chrysler 12%' },

                                 { x: "Nissan", y: 9, text:'Nissan 9%' }

                        ],



                        name: 'Car-Sale', labelPosition: 'outside', enableAnimation: true,

                        marker: { 

                            dataLabel:{ visible:true, connectorLine :{height :40}, font: {  size: '12px', color: "#707070"  } }						

                        }

                    }],

                    legend: { visible: false }



                };



            }



                    }

                    ],





                    legend: { visible: true },

                    AnimationComplete: false



                };

            }

        }

    &lt;/script&gt;



{ ![](User-Interactions_images/User-Interactions_img13.png) | markdownify }
{:.image }


Details about the first segment/slice in pie Chart:



{ ![](User-Interactions_images/User-Interactions_img14.png) | markdownify }
{:.image }


