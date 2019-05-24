---
layout: post
title: Multiple-Axes | PivotChart | ASP.NET | Syncfusion
description: This document illustrates that how to define multiple-axes and its properties in ASP.NET PivotChart control
platform: aspnet
control: PivotChart
documentation: ug
---

# Multiple Axes

You can split the pivot chart and its area into multiple panes to draw multiple series with multiple axes. Additional vertical/horizontal axes in the pivot chart can be created by the [`axes`](/api/js/ejpivotchart#members:axes) property.

Before rendering multiple axes in the pivot chart, you should know some important properties of axes and series of the pivot chart.

### Properties of axes

* **rowIndex**: Specifies the index of the row where the axis is associated.
* **columnIndex**: Specifies the index of the column where the axis is associated.
* **opposedPosition**: Specifies whether to render the axis at the opposite side of its default position.
* **labelFormat**: Provides custom formatting for axis label and supports all standard formatting types of numerical and date time values.
* **title**: You can customize the title of the axis by the following properties.
       * **enableTrim**: Specifies whether to trim the axis title when it exceeds the chart area or the maximum width of the title.
       * **maximumTitleWidth**: When the title exceeds the maximum width, the title gets trimmed by setting enableTrim to true.
       * **visible**: Controls the visibility of the axis title.
* **name**: Unique name of the axis. To associate an axis with the series, you have to set this name to the xAxisName/yAxisName property of the series.

To know more about axes properties, [`Click Here`](https://help.syncfusion.com/api/js/ejchart#members:axes)

### Properties of series

* **xAxisName**: Specifies the name of the X-axis that has to be associated with this series. Add an axis instance with this name to axes collection.
* **yAxisName**: Specifies the name of the Y-axis that has to be associated with this series. Add an axis instance with this name to axes collection.

## Customizing axes at row index of zero
You can customize the axes in the primary pivot chart itself. To achieve this, you should give the following properties:

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis RowIndex="0" Name="yAxisConfig"/>
  </Axes>
  <ClientSideEvents Load="onLoad" BeforeSeriesRender="onBeforeRender"/>
 </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

<script>

function onBeforeRender(args) {
 for (var i = 0; i < args.series.length; i++) {
    if (args.series[i].name.indexOf("Australia") != -1) {
       args.series[i].yAxisName = "yAxisConfig";
       args.series[i].type = "line";
  }
 }
return args;
}

</script>

{% endhighlight %}

![Axes customization at zeroth row index in ASP NET pivot chart control](Multiple_Axes_images/rowIndex_zero.png)

## Customizing axes at row index one

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis RowIndex="1" Name="yAxisConfig"/>
  </Axes>
  <ClientSideEvents Load="onLoad" BeforeSeriesRender="onBeforeRender"/>
 </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

<script>

function onBeforeRender(args) {
 for (var i = 0; i < args.series.length; i++) {
    if (args.series[i].name.indexOf("Australia") != -1) {
       args.series[i].yAxisName = "yAxisConfig";
       args.series[i].type = "line";
  }
 }
return args;
}
</script>

{% endhighlight %}

![Axes customization at first row index in ASP NET pivot chart control](Multiple_Axes_images/rowIndex_one.png)

## Customizing axes at column index of zero

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis ColumnIndex="0" Name="xAxisConfig"/>
  </Axes>
  <ClientSideEvents Load="onLoad" BeforeSeriesRender="onBeforeRender"/>
 </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

<script>

function onBeforeRender(args) {
 for (var i = 0; i < args.series.length; i++) {
    if (args.series[i].name.indexOf("Australia") != -1) {
       args.series[i].xAxisName = "xAxisConfig";
       args.series[i].type = "line";
  }
 }
return args;
}

</script>

{% endhighlight %}

![Axes customization at zeroth column index in ASP NET pivot chart control](Multiple_Axes_images/columnindex_zero.png)

## Customizing axes at column index of one

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis ColumnIndex="1" Name="xAxisConfig"/>
  </Axes>
  <ClientSideEvents Load="onLoad" BeforeSeriesRender="onBeforeRender"/>
 </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

<script>

function onBeforeRender(args) {
 for (var i = 0; i < args.series.length; i++) {
    if (args.series[i].name.indexOf("Australia") != -1) {
       args.series[i].xAxisName = "xAxisConfig";
       args.series[i].type = "line";
  }
 }
return args;
}
</script>

{% endhighlight %}

![Axes customization at first column index in ASP NET pivot chart control](Multiple_Axes_images/columnindex_one.png)

## Customizing series
You can customize the series in multiple axes support with the help of **beforeSeriesRender** event. You can change the series type through the **onBeforeRender** event.

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis Name="yAxisConfig"/>
  </Axes>
  <ClientSideEvents Load="onLoad" BeforeSeriesRender="onBeforeRender"/>
 </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

<script>

function onBeforeRender(args) {
 for (var i = 0; i < args.series.length; i++) {
    if (args.series[i].name.indexOf("Australia") != -1) {
       args.series[i].yAxisName = "yAxisConfig";
       args.series[i].type = "line";
  }
 }
return args;
}

</script>

{% endhighlight %}

**Note:** You have to use the same name in both name property of axes and xAxisName/yAxisName property of series in the above **beforeSeriesRender** event.

![Series customization in ASP NET pivot chart control](Multiple_Axes_images/customize_series.png)

To learn more about series properties, [`click here`](https://help.syncfusion.com/api/js/ejchart#members:series).


## Multiple axes support by series index

You can render the pivot chart with multiple axes by series index.

**Note:** This is the default behavior of multiple axes support, if you are not triggering the beforeSeriesRender event.

{% highlight html %}

<ej:PivotChart>
<%--....--%>
  <Axes>
    <ej:Axis Name="y:0"/>
    <ej:Axis Name="x:1"/>
  </Axes>
  </ej:PivotChart>

{% endhighlight %}

{% highlight javascript %}

 Name="y:0" => //you can create separate y axes for the series which you want
                //y indicates(yAxisName) axis in which series needs to be added.
                //0 indicates the series index of pivot chart.
                //you can also use pass multiple series index separated by comma(y:0,2)

 Name="x:1 =>  //you can create separate x axes for the series which you want
                 // x indicates(xAxisName) axis in which series needs to be added.
                 // 0 indicates the series index of pivot chart.
                 // you can also use pass multiple series index separated by comma(x:0,2)

{% endhighlight %}

### For Y-axes

{% highlight html %}

  <ej:PivotChart>
  <%--....--%>
  <Axes>
    <ej:Axis Name="y:0"/>
  </Axes>
  </ej:PivotChart>

{% endhighlight %}

![Series customization at zeroth index in ASP NET pivot chart control](Multiple_Axes_images/seriesindex_zero.png)

### For X-axes

{% highlight html %}

  <ej:PivotChart>
  <%--....--%>
  <Axes>
    <ej:Axis Name="x:0"/>
  </Axes>
  </ej:PivotChart>

{% endhighlight %}

![Series customization at first index in ASP NET pivot chart control](Multiple_Axes_images/seriesindex_one.png)

## Customizing PrimaryYAxis and axes properties

### labelFormat
You can customize the **labelFormat** for both PrimaryYAxis and custom axes.

{% highlight html %}

 <ej:PivotChart>
  <%--....--%>
  <Axes>
    <ej:Axis LabelFormat="n1"/>
  </Axes>
  <PrimaryXAxis LabelFormat="c">
  </PrimaryXAxis>
  </ej:PivotChart>

{% endhighlight %}

![Customization of label formats in ASP NET pivot chart control](Multiple_Axes_images/label_formats.png)

### title
You can customize the title for axes by the **title** property.

{% highlight html %}

 <ej:PivotChart>
  <%--....--%>
  <Axes>
    <ej:Axis Title-Text="Internet Sales Amount"/>
  </Axes>
  <PrimaryXAxis>
    <Title Text="Customer Count"></Title>
  </PrimaryXAxis>
  </ej:PivotChart>

{% endhighlight %}

![Customization of title in ASP NET pivot chart control](Multiple_Axes_images/title.png)
