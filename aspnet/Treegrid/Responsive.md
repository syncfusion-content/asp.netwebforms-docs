---
layout: post
title: Responsive | TreeGrid | ASP.NET | Syncfusion
description: Responsive
platform: aspnet
control: TreeGrid
documentation: ug
---

# Responsive

The TreeGrid control has support for responsive behavior based on client browser's width and height. To enable responsive support in TreeGrid, `IsResponsive` property must be enabled.

Please find the example describes the above behavior.

{% highlight html %}
 
<ej:TreeGrid ID="TreeGridContainer" IsResponsive="true">            
         //...     
</ej:TreeGrid>

{% endhighlight %}

The following output is displayed as a result of the above code example

![](Responsive_images/adaptive-mob.png)
{:caption}
Responsive TreeGrid in Mobile layout.

![](Responsive_images/adaptive.png)
{:caption}
Responsive TreeGrid in tablet layout.

## Layout

Below are the modes of responsive layout available in TreeGrid based on client width,

* Mobile(<321px)
* Tablet(321px to 768px)
* Desktop(>768px)

## Mobile Layout

The customized layout for filtering, column chooser operations and add/edit operations in mobile device can be seen in the following screen shots.

![](Responsive_images/adaptive-mob-filter.png)
{:caption}
filtering in mobile layout.

![](Responsive_images/adaptive-mob-edit.png)
{:caption}
Add/edit in mobile layout

![](Responsive_images/adaptive-mob-colchooser.png)
{:caption}
Column chooser in mobile layout

![](Responsive_images/adaptive-mob-insert.png)
{:caption}
Insert column options in mobile layout

## Tablet Layout

The customized layout for filtering, column chooser operations and add/edit operations in tablet device can be seen in the following screen shots.

![](Responsive_images/adaptive-filter.png)
{:caption}
filtering in tablet layout.

![](Responsive_images/adaptive-edit.png)
{:caption}
Add/edit in tablet layout

![](Responsive_images/adaptive-colchooser.png)
{:caption}
Column chooser in tablet layout

![](Responsive_images/adaptive-insert.png)
{:caption}
Insert column options in tablet layout

## Changing responsive width using method

You can change the minimum responsive width dynamically by using public method `updateResponsiveMinWidth(width)` by passing the width as an argument.
The TreeGrid control get works in responsive mode only when the window width is below the minimum responsive width.

Please find the example describes the above behavior.

{% highlight html %}
<button id="minResponsiveWidth">minResponsiveWidth</button>
<ej:TreeGrid ID="TreeGridContainer" IsResponsive="true">            
         //...     
</ej:TreeGrid>
{% endhighlight %}

{% highlight js %}
<script>

$("#minResponsiveWidth").click(function (args) {
    treegridObj = $("# TreeGridContainer ").data("ejTreeGrid");
    treegridObj.updateResponsiveMinWidth(600);
 });

</script>
{% endhighlight %}

The following output is displayed as a result of the above code example

![](Responsive_images/adaptive-publicmethod.png)

## Priority for columns

Column priorities are used to show or hide the columns based on priority values and browser width to best accommodate the possible columns. Priority value of the column is set by `Columns.Priority` property and the value ranges from one to six.

The following code example explains how to set priority for column

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer" IsResponsive="true">
    <ej:TreeGridColumn HeaderText="Task Id" Field="TaskID" Width="45" />
        <ej:TreeGridColumn HeaderText="Task Name" Field="TaskName" />
        <ej:TreeGridColumn HeaderText="Start Date" Field="StartDate" />
        <ej:TreeGridColumn HeaderText="End Date" Field="EndDate" Priority="5" />
        <ej:TreeGridColumn HeaderText="Duration" Field="Duration" Priority="6" />
        <ej:TreeGridColumn HeaderText="Progress" Field="Progress" Priority="6" /> 
</ej:TreeGrid>

{% endhighlight %}

![](Responsive_images/priority-column.png)

The above screen shot show TreeGrid rendered in browser width of 640 pixels.
{:.caption}