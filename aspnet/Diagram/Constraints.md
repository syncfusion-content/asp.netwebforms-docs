---
layout: post
title: Constraints | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to use the Constraints to enable or disable certain behaviors of the diagram, node, and connector.
platform: aspnet
control: Diagram
documentation: ug
---

# Constraints
Constraints are used to enable/disable certain behaviors of the diagram, node and connector. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled/disabled with bitwise operators (`&`, `|`, `~`, `<<`, etc.).
To know more about bitwise operators, refer to [Bitwise Operations](#bitwise-operations) 

## DiagramConstraints
Diagram constraints allow to enable or disable the following behaviors.

* Page Editing
* Line Bridging
* Zoom and Pan
* Undo Redo

For more information about Diagram constraints, refer to [Diagram Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.DiagramProperties.html#Syncfusion_JavaScript_DataVisualization_Models_DiagramProperties_Constraints "Diagram Constraints").

**Example**

The following example illustrates how to disable page editing.

{% tabs %}

{% highlight aspx-cs %}

  <ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%" >
  </ej:Diagram>
  
{% endhighlight %}

{% highlight c# %}

	protected void Page_Load(object sender, EventArgs e)
	{
		if (!IsPostBack)
		{
			//Set Diagram in read-only mode
			Diagram.Model.Constraints = DiagramConstraints.Default &~ DiagramConstraints.PageEditable;
		}
	}

{% endhighlight %}

{% endtabs %}

## NodeConstraints

NodeConstraints allows to enable or disable the following behaviors of node.

* Selection
* Deletion
* Drag
* Resize
* Rotate
* Connect
* Drop shadow
* Drag label
* Define tooltip

For more information about node constraints, refer to [Node Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.NodeBase.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_NodeBase_Constraints "Node Constraints")

**Example**

The following code illustrates how to disable rotation.

{% highlight c# %}

	protected void Page_Load(object sender, EventArgs e)
	{
		if (!IsPostBack)
		{
			//Disables rotation
			Node node = new Node(){ Constraints = NodeConstraints.Default &~ NodeConstraints.Rotate };
        	Diagram.Model.Nodes.Add(node);
		}
	}

{% endhighlight %}

## ConnectorConstraints

ConnectorConstraints allow to enable or disable certain behaviors of Connectors. They are as follows.

* Selection
* Deletion
* Drag
* Segment editing
* Define tooltip
* Bridging
* Label dragging

For more information about connector constraints, refer to [Connector Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Connector.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_Connector_Constraints "Connector Constraints")

**Example**

The following code illustrates how to disable selection.

{% highlight c# %}

	//Disables selection
	Connector connector = new Connector(){
		Name = "name",
		Constraints = ConnectorConstraints.Default &~ ConnectorConstraints.Select
	};
    Diagram.Model.Connectors.Add(connector);
	
{% endhighlight %}

## PortConstraints

You can enable or disable certain behaviors of Port. They are as follows.

* Connect

For more information about port constraints, refer to [Port Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Port.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_Port_Constraints "Port Constraints")

**Example**

The following code illustrates how to disable creating connections with a port.

{% highlight c# %}

	Node node = new Node(){ Name = "Node1"};
	node.Ports.Add(new Port() { Constraints = PortConstraints.None });
	Diagram.Model.Nodes.Add(node);

{% endhighlight %}

## SelectorConstraints

Selector visually represents the selected elements with certain editable thumbs. The visibility of the thumbs can be controlled with selector constraints. The part of selector is categorized as follows.

* Resizer
* Rotator
* User handles

For more information about Selector constraints, refer to [Selector Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.SelectedItems.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_SelectedItems_Constraints "Selector Constraints")

**Example**

The following code illustrates how to hide rotator.

{% highlight c# %}

	//Hides rotator
	Diagram.Model.SelectedItems = new SelectedItems(){
		Constraints = SelectorConstraints.All &~ SelectorConstraints.Rotator
	};
	
{% endhighlight %}

## SnapConstraints

Snap Constraints control the visibility of gridlines and enable/disable snapping. Snap constraints allow to set the following behaviors.

* Show only horizontal or vertical gridlines
* Show both horizontal and vertical gridlines
* Snap to either horizontal or vertical gridlines
* Snap to both horizontal and vertical gridlines

For more information about snap constraints, refer to [Snap Constraints](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.SnapSettings.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_SnapSettings_SnapConstraints "Snap Constraints")

**Example**

The following code illustrates how to show only horizontal gridlines.

{% highlight c# %}

	Diagram.Model.SnapSettings = new SnapSettings(){
		//Shows horizontal gridlines
		SnapConstraints = SnapConstraints.ShowHorizontalLines
	};
		
{% endhighlight %}

## Inherit behaviors

Some of the behaviors can be defined through both the specific object(node/connector) and Diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example illustrates how to inherit the line bridging behavior from the Diagram model.

{% highlight c# %}

	//Enables/disables line bridging based on the Diagram constraints
	Connector connector = new Connector() { Name = "Connector", SourcePoint = new DiagramPoint(100f, 100f), TargetPoint = new DiagramPoint(200f, 200f) };
	//Sets to inherit bridging from model
	connector.Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging;
	Diagram.Model.Connectors.Add(connector);
	
	//Enables line bridging for all connectors
	Diagram.Model.Constraints = DiagramConstraints.Default | DiagramConstraints.Bridging;

{% endhighlight %}


## Bitwise Operations

**Bitwise Operations** are used to manipulate the flagged enumerations [enum]. In this section, Bitwise Operations are illustrated by using node Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

### Add Operation

You can **add** or **enable** multiple values at a time by using **Bitwise** ‘\|’ (OR) **operator**.

{% highlight c# %}

node.Constraints = NodeConstraints.Select | NodeConstraints.Rotate;

{% endhighlight %}

In the above example, you can do both the selection and rotation.

### Remove Operation

You can **remove** or **disable** values by using **Bitwise** ‘&~’ (XOR) **operator**.

{% highlight c# %}

node.Constraints = node.Constraints & ~(NodeConstraints.Rotate);

{% endhighlight %}

In the above example, **Rotation** is disabled but other constraints are enabled.

### Check Operation

You can check any value by using **Bitwise** ‘&’ (AND) **operator**.

{% highlight c# %}

if ((node.Constraints & (NodeConstraints.Rotate)) == (NodeConstraints.Rotate))

{% endhighlight %}

In the above example, you can check whether the rotate constraints are enabled in a Node. When Node constraints have rotate constraints, the expression returns a rotate constraint.
