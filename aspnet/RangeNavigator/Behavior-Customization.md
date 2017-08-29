---
layout: post
title: Behavior Customization | RangeNavigator | ASP.NET | Syncfusion
description: behavior customization
platform: aspnet
control: RangeNavigator
documentation: ug
---

# Behavior Customization

RangeNavigator allows you to customize the control using events. You can change the range for selected data of the RangeNavigator using events.

## Deferred update

If you set EnableDeferredUpdate to true, the RangeChanged event gets fired after dragging and dropping the slider. By default the EnableDeferredUpdate is true. If EnableDeferredUpdate is false then the RangeChanged event gets fired while dragging the slider. 

{% highlight html %}
<ej:RangeNavigator ID="RangeNavigator1" runat="server" EnableDeferredUpdate="True" >

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %}

![](Behavior-Customization_images/Behavior-Customization_img1.png)

Deferred update
{:.caption}

## Handle Events

### Loaded: function

This event is handled when the RangeNavigator gets loaded. A parameter sender is passed to the handler. Using sender.model, you can access the RangeNavigator properties. 

{% tabs %}

{% highlight html %}
<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideLoaded="loadingData">

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %}

{% highlight js %}
<script type="text/javascript">

               function loadingData(sender) {

                     sender.model. isResponsive = false;

               }

</script>         
{% endhighlight %}

{% endtabs %}

### RangeChanged: function

This event gets fired whenever the selected range changes in RangeNavigator. A parameter sender is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 

{% tabs %}

{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="onChartLoad">

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>

{% endhighlight %}

{% highlight js %}
<script type="text/javascript">

    function onChartLoad(sender) {

         console.log(sender.selectedRangeSettings.start);

         }  

</script>     
{% endhighlight %}    

{% endtabs %}

## Use of ZoomCoordinates

RangeNavigator is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in RangeNavigator, you can use RangeChanged event of RangeNavigator and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the ZoomFactor and ZoomPosition of the RangeNavigator to the chart axis. 

{% tabs %}

{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="loadingData">

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %} 

{% highlight js %}
<script type="text/javascript">

  // setting zoom factor and position for chart axis in rangeChanged event.

     function loadingData(sender) {

         var chartObj = $("#RangeNavigator1").data("ejChart");

         if (chartObj != null) {

             chartObj.model.axes[0].zoomPosition = sender. zoomPosition;                                                               

             chartObj.model.axes[0].zoomFactor = sender. zoomFactor;

            }

            $("#RangeNavigator1").ejChart("redraw");

          }

</script>         
{% endhighlight %} 

{% endtabs %}

![](Behavior-Customization_images/Behavior-Customization_img2.png)

Use of ZoomCoordinates
{:.caption}

## Thumb Template

You can customize Thumb template by using LeftThumbTemplate and RightThumbTemplate property. You can add the required template as a “div” element with an “id” to the web page and assign the id or assign the HTML string to this property under NavigatorStyleSettings. 

{% tabs %}

{% highlight html %}
<script type="text/x-jsrender" id="left" >

           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black;">

                <path d="M2 2 L2 22 L22 22 L32 12 L22 2 Z" />

           </svg>

</script>

<script type="text/x-jsrender" id="right">

           <svg height="24" width="32" style="fill:#DD4A4A;stroke:black; ">

               <path d="M2 12 L12 22 L32 22 L32 2 L12 2 Z" />

           </svg>

</script>

{% endhighlight %} 

{% highlight js %}
<ej:RangeNavigator ID="Range1" runat="server"> 

// ...

<NavigatorStyleSettings LeftThumbTemplate="left" RightThumbTemplate=" right"/>

// ...

</ej:RangeNavigator>
{% endhighlight %} 

{% endtabs %}

The following screenshot displays the RangeNavigator using thumb template.

![](Behavior-Customization_images/Behavior-Customization_img3.png)

Thumb template
{:.caption}