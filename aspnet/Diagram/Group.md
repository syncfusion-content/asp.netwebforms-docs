---
layout: post
title: Group | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to use the Essential Diagram control Grouping functionality and its behavior in ASP.NET Webform.
platform: aspnet
control: Diagram
documentation: ug
---

# Group

Group is used to cluster multiple nodes and connectors into a single element. It acts like a container for its children (nodes, groups, and connectors). Every change made to the group also affects the children. Child elements can be edited individually. 

## Create Group

### Add group when initializing diagram

You can add a group to the Diagram model through `Nodes` collection. You can create Group like node and you need to add the child objects to the `Children` collection of the group. The following code illustrates how to create a group node.

{% highlight c# %}
BasicShape node1 = new BasicShape(){
    Name = "rectangle1",
    OffsetX = 100,
    OffsetY = 100,
    Width = 100,
    Height = 100,
    FillColor = "darkCyan",
    BorderWidth = 2, 
};
node1.Labels.Add(new Label() { Text = "Rectangle1" });
BasicShape node2 = new BasicShape()
{
    Name = "rectangle2",
    OffsetX = 200,
    OffsetY = 200,
    Width = 100,
    Height = 100,
    FillColor = "darkCyan",
    BorderWidth = 2,
};
node2.Labels.Add(new Label() { Text = "Rectangle2" });
Group group = new Group() { Name = "group1" };
group.Children.Add(node1);
group.Children.Add(node2);
Diagram.Model.Nodes.Add(group);
{% endhighlight %}

### Add group at run time

You can add a group node at runtime by using the client side method `add`.

The following code illustrates how a group node is added at run time.

{% highlight js %}
var group = {
	name: "group1",
	type: "group",
	children: [{
		name: "rectangle1",
		offsetX: 100,
		offsetY: 100,
		width: 100,
		height: 100,
		type: "node",
		fillColor: "darkCyan",
		borderWidth: 2,
		labels: [{
			text: "rectangle1"
		}]
	}, {
		name: "rectangle2",
		offsetX: 200,
		offsetY: 200,
		width: 100,
		height: 100,
		type: "node",
		fillColor: "darkCyan",
		borderWidth: 2,
		labels: [{
			text: "rectangle2"
		}]
	}]
};

var diagram = $("#DiagramContent").ejDiagram("instance");
// Adds group to the Diagram.
diagram.add(group);
{% endhighlight %}

### Group from palette

Group nodes can be predefined and added to symbol palette. You can drop those groups into Diagram, when required.

To explore how to add groups from symbol palette, refer to [Symbol Palette](/aspnet/Diagram/Symbol-Palette "Symbol Palette")

## Container

Containers are used to automatically measure and arrange the size and position of the child elements in a predefined manner.
There are two types of containers available.

### Canvas

* The Canvas panel supports absolute positioning and provides the least layout functionality to its contained Diagram elements. 
* Canvas allows you to position its contained elements by using margin and alignment properties.
* It allows elements to be either vertically or horizontally aligned.

The `Container` property of group should be defined and its `Type` should be set as `Canvas` to create a canvas panel. The following code illustrates how to add a canvas panel.

{% highlight c# %}
BasicShape node1 = new BasicShape()
{
    Name = "node1",
    FillColor = "darkCyan",
    Width = 100,
    Height = 100,
    MarginTop = 0,
    MarginLeft = 0,
};
BasicShape node2 = new BasicShape()
{
    Name = "node2",
    FillColor = "white",
    Width = 100,
    Height = 100,
    // Sets the margin to define the space around the child node.
    MarginTop = 30,
    MarginLeft = 30,
};
BasicShape node3 = new BasicShape()
{
    Name = "node3",
    FillColor = "darkCyan",
    Width = 100,
    Height = 100,
    MarginTop = 60,
    MarginLeft = 60,
};
BasicShape node4 = new BasicShape()
{
    Name = "node4",
    FillColor = "white",
    Width = 100,
    Height = 100,
    MarginTop = 90,
    MarginLeft = 90,
};
Group group = new Group()
{
    Name = "canvas",
    OffsetX = 400,
    OffsetY = 400,
    //Sets the container as canvas.
    Container = new Container() { Type = ContainerType.Canvas },
    FillColor = "#E7EBF4",
    BorderColor = "black",
    //Sets the padding to give space between the group border and group content.
    PaddingLeft = 30,
    PaddingTop = 30,
    PaddingRight = 30,
    PaddingBottom = 30,
};
group.Children.Add(node1);
group.Children.Add(node2);
group.Children.Add(node3);
group.Children.Add(node4);
Diagram.Model.Nodes.Add(group);
{% endhighlight %}

![add a canvas panel](/aspnet/Diagram/Group_images/Group_img9.png)

### Stack

* Stack panel is used to arrange its children in a single line or stack order, either vertically or horizontally.
* It controls spacing by setting margin properties of child and padding properties of group. By default, a Stack Panel’s `Orientation` is vertical. 

The `Container` property of group should be defined and its `Type` should be set as `Stack` to create a canvas panel The following code illustrates how to add a stack panel.

{% highlight c# %}
Node node1 = new Node() {
    Name = "node1", FillColor = "darkCyan", Width = 100, Height = 100,
    //Sets the horizontal Alignment for child node.
    HorizontalAlign = HorizontalAlignment.Left
};
Node node2 = new Node() { 
    Name = "node2", FillColor = "darkCyan", Width = 100, Height = 100,
    HorizontalAlign = HorizontalAlignment.Right
};
Node node3 = new Node()
{
    Name = "node3", FillColor = "darkCyan", Width = 100, Height = 100,
    HorizontalAlign = HorizontalAlignment.Stretch
};

Group group = new Group() {
    Name = "stack",
    OffsetX = 600,
    OffsetY = 200,

    //Sets the container as canvas.
    Container = new Container() { Type = ContainerType.Stack },
    FillColor = "#E7EBF4",
    BorderColor = "black",

    // Sets the minimum size for stack panel.
    MinHeight = 300,
    MinWidth = 300,
};
group.Children.Add(node1);
group.Children.Add(node2);
group.Children.Add(node3);
Diagram.Model.Nodes.Add(group);
{% endhighlight %}

![add a stack panel](/aspnet/Diagram/Group_images/Group_img10.png)

## Difference between a basic group and containers

| Group | Container |
|---|---|
| It arranges the child elements based on the child elementâ??s position and size properties. | Each container has a predefined behaviour to measure and arrange its child elements. Canvas and stack containers are supported in the Diagram. |
| Padding, Min and Max Size properties are not applicable for basic group. | It is applicable for container. |
| Children's margin and alignment properties are not applicable for basic group. | It is applicable for container. |

## Interaction

You can edit the group and its children at runtime. For more information about how to interact with a group, refer to [Edit Groups](/aspnet/Diagram/Interaction#selection "Interaction").