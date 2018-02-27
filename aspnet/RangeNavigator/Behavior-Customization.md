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

If you set `EnableDeferredUpdate` to true, the `RangeChanged` event gets fired after dragging and dropping the slider. By default the EnableDeferredUpdate is true. If EnableDeferredUpdate is false then the RangeChanged event gets fired while dragging the slider. 

{% highlight html %}
<ej:RangeNavigator ID="RangeNavigator1" runat="server" EnableDeferredUpdate="true" >

<%--Code --%>

<%--Code --%>

</ej:RangeNavigator>
{% endhighlight %}

![](Behavior-Customization_images/Behavior-Customization_img1.png)

Deferred update
{:.caption}

## Methods

### _destroy

This method is used to destroy the **RangeNavigator** widget. 

{% highlight html %}
 
<ej:RangeNavigator ID="RangeNavigator1" runat="server">
</ej:RangeNavigator>

<script type="text/javascript"> 
    // destroy the range navigator
     $("#RangeNavigator1").ejRangeNavigator("_destroy"); 
</script>

{% endhighlight  %}

## Handle Events

### Load

This event is fired when **RangeNavigator** is loading. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideLoad="loadData">

</ej:RangeNavigator>

{% endhighlight %}

{% highlight js %}

<script type="text/javascript">

	function loadData(sender) 
	{

		 sender.model.allowSnapping = false;

	}

</script>

{% endhighlight %}



### Loaded

This event is handled when the RangeNavigator gets loaded. A parameter sender is passed to the handler. Using sender.model, you can access the RangeNavigator properties. 



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



### RangeChanged

This event gets fired whenever the selected range changes in RangeNavigator. A parameter sender is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 



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



### SelectedRangeStart

This event is fired when starting to change the slider position in **RangeNavigator**. A parameter **sender** is passed to the handler. Using **sender.selectedRangeSettings**, you can access the start value of range for the selected region. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideSelectedRangeStart="selectedRangeStart">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function selectedRangeStart(sender) 
   {

		 console.log(sender.selectedRangeSettings.start);

   }

</script>   

{% endhighlight %}



### SelectedRangeEnd

This event is fired when selection ends in **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.selectedRangeSettings, you can access the end value of range for the selected region. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideSelectedRangeEnd="selectedRangeEnd">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function selectedRangeEnd(sender) 
   {

		 console.log(sender.selectedRangeSettings.end);

   }

</script>   

{% endhighlight %}



### ScrollStart

This event is fired when starting to change the scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.data startRange and sender.data endRange, you can access the scrollbar position starting and ending range value on changed scrollbar. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideScrollStart="scrollStart">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function scrollStart(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}



### ScrollEnd

This event is fired while ending the change in scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using data oldRange and data newRange, you can access the scrollbar position old and new range values on changing scrollbar. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideScrollEnd="scrollEnd">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function scrollEnd(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}



### ScrollChanged

This event is fired when changing the scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using data oldRange and data newRange, you can access the old and new range values of changed scrollbar position. 



{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideScrollChanged="scrollChanged">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function scrollChanged(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}


### Click

`Click` event is handled when the **RangeNavigator** gets clicked. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 


{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideClick="click">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function click(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}


### DoubleClick

`DoubleClick` event is handled when the **RangeNavigator** gets clicked. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 


{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideDoubleClick="doubleClick">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function doubleClick(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}

### RightClick

`RightClick` event is handled when the **RangeNavigator** gets clicked. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 


{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRightClick="rightClick">

</ej:RangeNavigator>

{% endhighlight %}    

{% highlight js %}

<script type="text/javascript">

   function rightClick(sender) 
   {
	   	console.log(sender.type);
   }

</script>  

{% endhighlight %}


## Use of ZoomCoordinates

RangeNavigator is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in RangeNavigator, you can use `RangeChanged` event of RangeNavigator and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the  `ZoomFactor` and `ZoomPosition` of the RangeNavigator to the chart axis. 



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



![](Behavior-Customization_images/Behavior-Customization_img2.png)

Use of ZoomCoordinates
{:.caption}

## Thumb Template

You can customize Thumb template by using `LeftThumbTemplate` and `RightThumbTemplate` property. You can add the required template as a “div” element with an “id” to the web page and assign the id or assign the HTML string to this property under `NavigatorStyleSettings`. 



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



The following screenshot displays the RangeNavigator using thumb template.

![](Behavior-Customization_images/Behavior-Customization_img3.png)

Thumb template
{:.caption}

## Value Axis Settings

You can customize the line, `Font` `Size`, gridline, tickline, range, `RangePadding` and visibility of **RangeNavigator** axis.

To enable the visibility of axis line, you need to set `Visible` property of `AxisLine` in `ValueAxisSettings`. 

You can customize the axis range by specifying `Min`, `Max` and `Interval` for `Range` property.

The `MajorGridLines` can be enabled by specifying `Visible` property. The `Size`, `Width` and `Visible` property of `MajorTickLines` is used to customize the axis tick lines.

The visibility of `ValueAxisSettings` is enabled by setting `Visible` property as true. 

{% highlight html %}

<ej:RangeNavigator ID="Range1" runat="server">
    <ValueAxisSettings RangePadding="Normal" Visible="true">
        <AxisLine Visible="true"></AxisLine>
        <Font Size="12px"></Font>
        <MajorGridLines Visible="true"></MajorGridLines>
		<MajorTickLines Size="3" Visible="false" Width="3"></MajorTickLines>
        <Range Min="0" Max="100" Interval="10"></Range>
    </ValueAxisSettings>           
</ej:RangeNavigator>

{% endhighlight %}

## Selected Range Settings

The start and end range values of selected range can be customized using `Start` and `End` property of `SelectedRangeSettings`.

{% highlight html %}

<ej:RangeNavigator ID="Range1" runat="server">
    <SelectedRangeSettings Start="01/05/1992" End="01/05/1993">
    </SelectedRangeSettings>           
</ej:RangeNavigator>  

{% endhighlight %}