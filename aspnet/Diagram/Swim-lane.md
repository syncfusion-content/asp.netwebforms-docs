---
layout: post
title: Swim-lane
description: swim lane 
platform: aspnet
control: Diagram
documentation: ug
---

# Swim lane 

A swim lane is a visual element used in a process flow diagrams or flowcharts. A typical swim lane contains a header, and a collection of lanes that can be arranged horizontally or vertically.

  ![](Swim-lane_images/Swim-lane_img1.png) 



Swim lane shape contains the following properties.

_Swim lane Properties_

<table>
<tr>
<th>
Property</th><th>
Data type</th><th>
Description</th></tr>
<tr>
<td>
Header</td><td>
Object</td><td>
Gets or sets the header value of the swim lane.</td></tr>
<tr>
<td>
Orientation</td><td>
String</td><td>
Gets or sets the orientation of the swim lane.</td></tr>
<tr>
<td>
OffsetX</td><td>
Int</td><td>
Gets or sets the offsetX value of the swim lane.</td></tr>
<tr>
<td>
OffsetY</td><td>
Int</td><td>
Gets or sets the offsetY value of the swim lane.</td></tr>
<tr>
<td>
MinHeight</td><td>
Int</td><td>
Gets or sets the minHeight value of the swim lane.</td></tr>
<tr>
<td>
MinWidth</td><td>
Int</td><td>
Gets or sets the minWidth value of the swim lane.</td></tr>
<tr>
<td>
MaxHeight</td><td>
Int</td><td>
Gets or sets the maxHeight value of the swim lane.</td></tr>
<tr>
<td>
MaxWidth</td><td>
Int</td><td>
Gets or sets the maxWidth value of the swim lane.</td></tr>
<tr>
<td>
Lanes</td><td>
Array</td><td>
Gets or sets the lanes as collection.</td></tr>
<tr>
<td>
Phases</td><td>
Array</td><td>
Gets or sets the phases as collection.</td></tr>
</table>


## Lane

The lane is an object that controls the diagram elements in the swim lane. Lane has the following properties.

_Lane Properties_

<table>
<tr>
<th>
Property</th><th>
Data type</th><th>
Description</th></tr>
<tr>
<td>
Header</td><td>
Object</td><td>
Gets or sets the lane header.</td></tr>
<tr>
<td>
Name</td><td>
String</td><td>
Gets or sets the name of the header.</td></tr>
<tr>
<td>
Children</td><td>
Array</td><td>
Gets or set the child nodes as collection.</td></tr>
<tr>
<td>
Orientation</td><td>
String</td><td>
Gets or sets the orientation of the swim lane.</td></tr>
</table>


## Header

This is used to define header of a swim lane. It has the following properties.

_Header Properties_

<table>
<tr>
<th>
Property</th><th>
Data type</th><th>
Description</th></tr>
<tr>
<td>
Width</td><td>
Int</td><td>
Gets or sets the width of the header.</td></tr>
<tr>
<td>
Text</td><td>
String</td><td>
Gets or sets the text value for the header.</td></tr>
</table>


## Phase

A Phase is a line that separates the swim lane. Phase has the following properties.

_Phase Properties_

<table>
<tr>
<th>
Property</th><th>
Data type</th><th>
Description</th></tr>
<tr>
<td>
Name</td><td>
String</td><td>
Gets or set the name of the phase.</td></tr>
<tr>
<td>
Offset</td><td>
Int</td><td>
Gets or set the offset value of the phase.</td></tr>
<tr>
<td>
LineWidth</td><td>
Int</td><td>
Gets or set the stroke width of the phase.</td></tr>
<tr>
<td>
LineDashArray</td><td>
String</td><td>
Gets or set the stroke dash array of the phase.</td></tr>
<tr>
<td>
LineColor</td><td>
String</td><td>
Gets or set the stroke colour of the phase.</td></tr>
<tr>
<td>
Parent</td><td>
String</td><td>
Gets or sets the parent of the phase</td></tr>
</table>


The following code illustrates how to create a simple swim lane.

{% highlight c# %}

        private void GenerateNodes(DiagramProperties diagram)

        {

            SwimLane swimlane = new SwimLane();

            swimlane.Type = "swimlane";

            swimlane.Name = "swimlane";

            Header header = new Header();

            header.Text = "HEADER";

            header.Height = 50;

            header.FillColor = "#C7D4DF";

            header.FontSize = 11;

            swimlane.Header = header;

            swimlane.FillColor = "#C7D4DF";

            swimlane.Orientation = "horizontal";

            swimlane.OffsetX = 350;

            swimlane.OffsetY = 290;

            swimlane.Height = 100;

            swimlane.Width = 450;

            swimlane.Lanes = CreateLanes();

            diagram.Nodes.Add(swimlane);

        }



        private Collection CreateLanes()

        {

            Collection lanCol = new Collection();

            Collection childCollec = new Collection();

            childCollec.Add(createNode("Order1", "Node1", 100, 10));

            childCollec.Add(createNode("Order2", "Node1", 250, 10));

            lanCol.Add(CreateLane("stackCanvas1", "HEADER", "#f5f5f5",

                                   childCollec));

            return lanCol;

        }

        private Node createNode(string name, string label, 

                                double mLeft, double mTop)

        {

            Node node = new Node();

            node.Name = name;

            node.Width = 100;

            node.Height = 40;

            node.Labels.Add(new Label() { Name = name, Text = label });

            node.MarginLeft = mLeft;

            node.MarginTop = mTop;

            return node;

        }



        private Lane CreateLane(string name, string hText,

                            string fillColor, Collection children)

        {

            Lane lane = new Lane();

            lane.Name = name;

            Header header = new Header();

            header.Text = hText;

            header.Width = 50;

            header.FillColor = "#C7D4DF";

            header.FontSize = 11;

            lane.FillColor = "#f5f5f5";

            lane.Header = header;

            lane.Height = 120;

            lane.Children = children;

            return lane;

        }



{% endhighlight %}



