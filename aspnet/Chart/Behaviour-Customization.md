---
layout: post
title: Behaviour-Customization
description: behaviour customization
platform: aspnet
control: Chart
documentation: ug
---

## Behaviour Customization

Essential Chart allows you to customize the Chart through events. For example, you can add custom marker for highest and lowest data point using the events.

### Select a point

You can acquire the information related to a particular data point of series by moving mouse over the point or by clicking the point using PointRegionMouseMove or PointRegionClick event. PointRegionMouseMove event gets triggered when you move the mouse over the point and the PointRegionClick event gets triggered when you click the point. The following code example illustrates that x and y values of a point gets displayed when you move the mouse over the point or click the point.



[ASP.NET] 

 &lt;ej:Chart ID="Chart1"  OnClientPointRegionClick="pointDetails" OnClientPointRegionMouseMove="pointDetails" runat="server"&gt;



     &lt;CommonSeriesOptions Type="Column"&gt;&lt;/CommonSeriesOptions&gt;        



 &lt;/ej:Chart&gt;

[JS]

  &lt;script type="text/javascript"&gt;

 function pointDetails(sender) {

     series = sender.model.series[sender.data.region.SeriesIndex];

     var X = series.points[sender.data.region.Region.PointIndex].x;

     var Y = series.points[sender.data.region.Region.PointIndex].y;

     alert("X:" + X + "  Y:" + Y);

    }

  &lt;/script&gt;



{ ![](Behaviour-Customization_images/Behaviour-Customization_img1.png) | markdownify }
{:.image }


### Handle Events

Chart Events:

Load: function

This event is handled when the Chart gets loaded; a parameter sender is passed to the handler. Using sender.model, you can access the Chart properties except series that were passed to the chart. 



[ASP.NET] 

  &lt;ej:Chart ID="Chart1" OnClientLoad="onload" runat="server"&gt;

  &lt;/ej:Chart&gt;

[JS]

     &lt;script type="text/javascript"&gt;

               function onload (sender) {

                     sender.model.canResize = false;

               }

      &lt;/script&gt;       



PreRender: function

This event is handled before the Chart gets rendered; a parameter sender is passed to the handler. Using sender.model, you can access the Chart properties that were passed to the Chart. 



[ASP.NET] 

  &lt;ej:Chart ID="Chart1"  OnClientPreRender="onprerender" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onprerender (sender) {

             console.log(sender.model.series.length);

         }     

 &lt;/script&gt;         





TitleRendering: function

This event is handled before the Chart title gets rendered; a parameter sender is passed to the handler. Using sender.data.title, you can change the title of the Chart after the Chart is loaded.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientTitleRendering="ontitleRendering" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function ontitleRendering(sender) {

               sender.data.title = "Olympic";

               }

&lt;/script&gt;         





ChartAxis Events:

AxesLabelsInitialize: function

This event is handled before the Chart axis gets rendered; a parameter sender is passed to the handler. Using sender.data.axes, you can change the axis related properties after the Chart is loaded.



[ASP.NET] 

&lt;ej:Chart ID="Chart1 OnClientAxesLabelsInitialize="onaxesLabelsInitialize" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onaxesLabelsInitialize(sender) {

             sender.data.axes[0].orientation = "horizontal";

               }

&lt;/script&gt;         





AxesRangeCalculate: function

This event is handled after the Chart axis range gets calculated; a parameter sender is passed to the handler. Using sender.data.range, you can change the range calculated for the Chart axis.



[ASP.NET] 

&lt;ej:Chart ID="Chart1"  OnClientAxesRangeCalculate="onaxesRangeCalculate"  runat="server"&gt;



   &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onaxesRangeCalculate(sender) {

             sender.data.range.min = 2;

               }

&lt;/script&gt;         





AxesTitleRendering: function

This event is handled before the Chart axis title gets rendered; a parameter sender is passed to the handler. Using sender.data.Title, you can change the axis title after the Chart is loaded.



[ASP.NET] 

  &lt;ej:Chart ID="Chart1" OnClientTitleRendering="onaxesTitleRendering" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

           function onaxesTitleRendering(sender) {

             sender.data.title = "Countries";

             }

&lt;/script&gt;         





AxesLabelRendering: function

This event is handled before the Chart axis label gets rendered; a parameter sender is passed to the handler. Using sender.data.label.Text, you can change the axis labels after the Chart is loaded.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientAxesLabelRendering="onaxesLabelRendering"  runat="server"&gt;



    &lt;/ej:Chart&gt;

[JS]

     &lt;script type="text/javascript"&gt;

         function onaxesLabelRendering(sender) {

             sender.data.label.Text = "Label1";

               }

      &lt;/script&gt;



Series Events:

SeriesRendering: function

This event is handled before the Chart series gets rendered; a parameter sender is passed to the handler. Using sender.data.series, you can get access to the series properties.



[ASP.NET] 

  &lt;ej:Chart ID="Chart1"  OnClientSeriesRendering="onseriesRendering" runat="server"&gt;



   &lt;/ej:Chart&gt;

[JS]

     &lt;script type="text/javascript"&gt;

        function onseriesRendering(sender) {

             sender.data.series.name = "horizontal";

          }

      &lt;/script&gt;





SymbolRendering: function

This event is handled before the marker of each series point gets rendered; a parameter sender is passed to the handler. Using sender.data you can get access style and location of the symbol.



[ASP.NET] 

  &lt;ej:Chart ID="Chart1" OnClientSymbolRendering="onsymbolRendering" runat="server"&gt;



    &lt;/ej:Chart&gt;

[JS]

     &lt;script type="text/javascript"&gt;

         function onsymbolRendering(sender) {

             console.log(sender.data.style.PointIndex);

          }

      &lt;/script&gt;





DisplayTextRendering: function

This event is handled before the dataLabel of each series points gets rendered; a parameter sender is passed to the handler. Using sender.data.text you can change the dataLabel of each point in the series.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientDisplayTextRendering="ondisplayTextRendering" runat="server"&gt;



 &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

        function ondisplayTextRendering(sender) {

                 sender.data.text = "34";

           }

      &lt;/script&gt;





AnimationComplete: function

This event is handled after the series animation is completed; a parameter sender is passed to the handler.  





[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientAnimationComplete="onanimationComplete" runat="server"&gt;



 &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

     function onanimationComplete(sender) {

             console.log(sender.data.series.name);

       }

      &lt;/script&gt;



Legend Events:

LegendItemRendering: function

This event is handled before the legend of each series points gets rendered; a parameter sender is passed to the handler. Using sender.data.legendItem.Text you can change the text of each legend text.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientLegendItemRendering=" onlegendItemRendering " runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onlegendItemRendering(sender) {

             sender.data.legendItem.Text = "Series1";

         }



      &lt;/script&gt;





LegendItemClick: function

This event is handled when you click the legend item; a parameter sender is passed to the handler.  



[ASP.NET] 

&lt;ej:Chart ID="Chart1"  OnClientLegendItemClick="onlegendItemClick" runat="server"&gt;



&lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onlegendItemClick(sender) {

             console.log("Legend Item Click");

         }

     &lt;/script&gt;





LegendItemMouseMove: function

This event is handled when you move the mouse over the legend item; a parameter sender is passed to the handler. Using sender.data.legendItem.Text you can change the text of each legend text.



[ASP.NET] 

&lt;ej:Chart ID="Chart1"  OnClientLegendItemMouseMove="onlegendItemMouseMove" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onlegendItemMouseMove(sender) {

             console.log("Legend Item Mouse Move");

         }

      &lt;/script&gt;





LengendBoundsCalculate: function

This event is handled after the bounds for legend is calculated.  A parameter sender is passed to the handler.  Using sender.data.legendBound, you can access the bounds of the Chartlegend.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientLengendBoundsCalculate="onlegendBoundsCalculate" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function onlegendBoundsCalculate(sender) {

             sender.data.legendBound.Height = 34;

         }

      &lt;/script&gt;





Tooltip Events:

ToolTipInitialize: function

This event is handled before the tooltip gets rendered.  A parameter sender is passed to the handler.  Using sender.data.currentText, you can change the tooltip text.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientToolTipInitialize="ontoolTipInitialize" runat="server"&gt;



    &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

        function ontoolTipInitialize(sender) {

             sender.data.currentText = "tooltip";

         }

      &lt;/script&gt;





TrackAxisToolTip: function

This event is handled before the tooltip for axis gets rendered when crosshair is enabled.  A parameter sender is passed to the handler.  Using sender.data.currentTrackText, you can change the tooltip text.



[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientTrackAxisToolTip="ontrackAxisToolTip" runat="server"&gt;



  &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

         function ontrackAxisToolTip(sender) {

             sender.data.currentTrackText = "tooltip";

         }

      &lt;/script&gt;         





TrackToolTip: function

This event is handled before the tooltip for trackball get rendered when trackball is enabled.  A parameter sender is passed to the handler.  Using sender.data.currentText, you can change the tooltip text.





[ASP.NET] 

  &lt;ej:Chart ID="Chart1"  OnClientTrackToolTip="ontrackToolTip" runat="server"&gt;



 &lt;/ej:Chart&gt;

 [JS]

     &lt;script type="text/javascript"&gt;

        function ontrackToolTip(sender) {

             sender.data.currentText = "tooltip";

         }

      &lt;/script&gt;





