---
layout: post
title: Add gridlines behind nodes and connectors to ease alignments
description: How to add gridlines behind nodes and connectors?
platform: aspnet
control: Diagram
documentation: ug
---

# Gridlines

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

## Customize the gridlines visibility

The `SnapSettings.SnapConstraints` enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

{% highlight html %}
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%">
	<%--Shows both horizontal and vertical gridlines--%>
	<SnapSettings SnapConstraints="ShowLines" />
</ej:Diagram> 
{% endhighlight %}

![](/Gridlines_images/Gridlines_img1.png)

To show only horizontal/vertical gridlines or to hide gridlines, refer to [Constraints](/js/Diagram/Constraints#snapconstraints "Constraints")

## Appearance

You can customize the appearance of the gridlines by using a set of predefined properties. To explore those properties, refer to [Gridlines](/js/api/ejDiagram#snapsettings:horizontalgridlines "Gridlines")
The `HorizontalGridLines` and `VerticalGridLines` properties allow to customize the appearance of the gridlines. The following code example illustrates how to customize the appearance of gridlines.

{% highlight html %}
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%">
	<SnapSettings SnapConstraints="ShowLines">
		<HorizontalGridlines LineColor="blue" LineDashArray="2 2"></HorizontalGridlines>
		<VerticalGridlines LineColor="blue" LineDashArray="2 2"></VerticalGridlines>
	</SnapSettings>
</ej:Diagram>
{% endhighlight %}

![](/Gridlines_images/Gridlines_img4.png)

### Line Intervals

Thickness and the space between gridlines can be customized by using `LinesInterval` property. In the linesInterval collections, values at the odd places are refered as the thickness of lines and the values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% highlight c# %}
List<decimal> intervals = new List<decimal>();
intervals.Add(1.25m);
intervals.Add(14);
intervals.Add(0.25m);
intervals.Add(15);
intervals.Add(0.25m);
intervals.Add(15);
intervals.Add(0.25m);
intervals.Add(15);
intervals.Add(0.25m);
intervals.Add(15);
Diagram.Model.SnapSettings = new SnapSettings()
{
	//Shows both horizontal and vertical gridlines
	SnapConstraints = SnapConstraints.ShowLines,
	// Customizes the line color and line style to the gridlines.
	// Defines the thickness and intervals for a pattern of lines
	HorizontalGridlines = new GridLines() {
		LinesInterval = intervals,
		LineColor = "blue",
		LineDashArray = "2 2"
	},
	VerticalGridlines = new GridLines() {
		LinesInterval = intervals,
		LineColor = "blue",
		LineDashArray = "2 2"
	}
};
{% endhighlight %}

![](/Gridlines_images/Gridlines_img2.png)

# Snapping

## Snap To Lines

This feature allows the Diagram objects to snap to the nearest intersection of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the `SnapSettings.SnapConstraints`. The following code example illustrates how to enable/disable the snapping to gridlines.

{% highlight html %}
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%">
	<%--Enables snapping to both the horizontal and vertical lines.--%>
	<SnapSettings SnapConstraints="SnapToLines" />
</ej:Diagram> 
{% endhighlight %}

To enable/disable snapping to horizontal/vertical lines, refer to [Constraints] (/js/Diagram/Constraints#SnapConstraints "Constraints")

## Customization of Snap Intervals

By default, the objects are snapped towards the nearest gridline. The gridline or position towards where the diagram object snaps can be customized with the property, `snapInterval`. The following code example illustrates how to customize the snap intervals.

{% highlight c# %}
List<decimal> interval = new List<decimal>();
interval.Add(10);
//Enables snapping to both the horizontal and vertical lines.
Diagram.Model.SnapSettings = new SnapSettings()
{
	HorizontalGridlines = new GridLines() { SnapInterval = interval },
	VerticalGridlines = new GridLines() { SnapInterval = interval },
	SnapConstraints = SnapConstraints.All
};
{% endhighlight %}

## Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram elements. A node can be snapped with its neighbouring objects based on certain alignments. Such alignments are visually represented as smart guides.

The `EnableSnapToObject` property allows you to enable/disable smart guides. The following code example illustrates how to enable/disable the smart guides.

{% highlight html %}
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%">
	<%--Enables snapping to both the horizontal and vertical lines.--%>
	<SnapSettings EnableSnapToObject=true />
</ej:Diagram> 
{% endhighlight %}

![](/Gridlines_images/Gridlines_img4.png)