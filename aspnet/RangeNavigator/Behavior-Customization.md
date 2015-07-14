---
layout: post
title: Behavior-Customization
description: behavior customization
platform: aspnet
control: RangeNavigator
documentation: ug
---

## Behavior Customization

RangeNavigator allows you to customize the control using events. You can change the range for selected data of the RangeNavigator using events.

Deferred update

If you set EnableDeferredUpdate to true, the RangeChanged event gets fired after dragging and dropping the slider. By default the EnableDeferredUpdate is true. If EnableDeferredUpdate is false then the RangeChanged event gets fired while dragging the slider. 

 [ASP.NET]

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" EnableDeferredUpdate="True" &gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;


{ ![](Behavior-Customization_images/Behavior-Customization_img1.png) | markdownify }
{:.image }


_Figure 19: Deferred update_

Handle Events

Loaded: function

This event is handled when the RangeNavigator gets loaded. A parameter sender is passed to the handler. Using sender.model, you can access the RangeNavigator properties. 

 [ASP.NET]

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideLoaded="loadingdata"&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

[JS]

&lt;script type="text/javascript"&gt;

               function loadingdata(sender) {

                     sender.model. enableAutoResizing = false;

               }

  &lt;/script&gt;         


RangeChanged: function

This event gets fired whenever the selected range changes in RangeNavigator. A parameter sender is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 

 [ASP.NET]

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="onchartload"&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

[JS]

&lt;script type="text/javascript"&gt;

    function onchartload(sender) {

         console.log(sender.selectedRangeSettings.start);

         }  

&lt;/script&gt;         

Use of ZoomCoordinates

RangeNavigator is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in RangeNavigator, you can use RangeChanged event of RangeNavigator and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the ZoomFactor and ZoomPosition of the RangeNavigator to the chart axis. 

 [ASP.NET]

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="loadingdata"&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

[JS]

&lt;script type="text/javascript"&gt;

  // setting zoom factor and position for chart axis in rangeChanged event.

     function loadingdata(sender) {

         var chartobj = $("#RangeNavigator1").data("ejChart");

         if (chartobj != null) {

             chartobj.model.axes[0].zoomPosition = sender. zoomPosition;                                                               

             chartobj.model.axes[0].zoomFactor = sender. zoomFactor;

            }

            $("#RangeNavigator1").ejChart("redraw");

          }

      &lt;/script&gt;         



{ ![](Behavior-Customization_images/Behavior-Customization_img2.png) | markdownify }
{:.image }


Thumb Template

You can customize Thumb template by using LeftThumbTemplate and RightThumbTemplate property. You can add the required template as a “div” element with an “id” to the web page and assign the id or assign the html string to this property under NavigatorStyleSettings. 

[ASP]

&lt;script type="text/x-jsrender" id="left" &gt;

           &lt;svg height="24" width="32" style="fill:#DD4A4A;stroke:black;"&gt;

                &lt;path d="M2 2 L2 22 L22 22 L32 12 L22 2 Z" /&gt;

           &lt;/svg&gt;

&lt;/script&gt;

&lt;script type="text/x-jsrender" id="right"&gt;

           &lt;svg height="24" width="32" style="fill:#DD4A4A;stroke:black; "&gt;

               &lt;path d="M2 12 L12 22 L32 22 L32 2 L12 2 Z" /&gt;

           &lt;/svg&gt;

&lt;/script&gt;

[CS] 

 &lt;ej:RangeNavigator ID="Range1" runat="server"&gt; 



      // ...



     &lt;NavigatorStyleSettings LeftThumbTemplate="left" RightThumbTemplate=" right"/&gt;



      // ...



 &lt;/ej:RangeNavigator&gt;



The following screenshot displays the RangeNavigator using thumb template.

{ ![D:/TRUNK LOCATION/Feature Tool/Image/aspnet/ejrangenavigator/Chart-Customization.png](Behavior-Customization_images/Behavior-Customization_img3.png) | markdownify }
{:.image }


