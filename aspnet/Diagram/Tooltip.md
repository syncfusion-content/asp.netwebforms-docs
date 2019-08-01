---
layout: post
title: Tooltip | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to show/hide tooltips when mouse hovers over objects or during interaction.
platform: aspnet
control: Diagram
documentation: ug
---

# Tooltip
In Graphical User Interface (GUI), tooltip is a message that is displayed when mouse hovers over an element. Diagram provides tooltip support while dragging, resizing, rotating a node, and when mouse hovers any Diagram element.

## Default tooltip

By default, Diagram displays a tooltip to provide the size, position, and angle related information while dragging, resizing, and rotation. The following images illustrate how the Diagram displays the node information during interaction.

| Drag | Resize | Rotate |
|---|---|---|
| ![displays the node dragging information](/aspnet/Diagram/Tooltip_images/Tooltip_img1.png) | ![displays the node resizing information](/aspnet/Diagram/Tooltip_images/Tooltip_img2.png) | ![displays the node rotation information](/aspnet/Diagram/Tooltip_images/Tooltip_img3.png) |

### Disable default tooltip

To disable the default tooltip, You need to set `SelectedItems.Tooltip` as `null`. The following code example illustrates how to disable default tooltip.

{% tabs %}
{% highlight aspx-cs %}

        <!--Define tooltip template-->       
        <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px">
           
        </ej:Diagram>
        
{% endhighlight %}

{% highlight c# %}

            //Disable tooltip during interaction
             Diagram.Model.SelectedItems.Tooltip = null;
             
{% endhighlight %} 
{% endtabs %} 

## Common tooltip for all nodes and connectors

Diagram provides support to show tooltip when mouse hovers over any node/connector. 
To show tooltip on mouse over, the `Tooltip` property of Diagram model needs to be set with the tooltip `TemplateId` and `Alignment` as shown in the following example.

 {% tabs %}
 {% highlight aspx-cs %}

        <!--Define tooltip template-->
        <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
            <span style="padding: 5px;"> {{"{{"}}:addInfo.Description{{}}}} </span>
        </div>
        </script>

 
        <%--   Initializes Diagram--%>
        <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" OnClientCreate="diagramCreate" Height="600px" Width="1000px" Locale="en-US" EnableContextMenu="true">
                 <Tooltip TemplateId="mouseovertooltip"></Tooltip>
        <PageSettings ScrollLimit="Diagram" />
        <SnapSettings SnapConstraints="None" />
     
    </ej:Diagram> 
        
{% endhighlight %}
{% highlight c# %}
public partial class DiagramFeatures: System.Web.UI.Page {
    protected void Page_Load(object sender, EventArgs e) {
        Node node = CreateNode(DiagramWebControl1.Nodes, "node1", 60, 60, 100, 100, "Elizabeth", "Managing Director");

    }

    private Node CreateNode(Collection nodes, String name, double width, double height, double offsetx, double offsety, string text = "", string description = "") {
        Node node = new Node();
        node.Name = name;
        node.Width = width;
        node.Height = height;
        node.OffsetX = offsetx;
        node.OffsetY = offsety;
        Label label = new Label();
        label.Text = text;
        label.FontColor = "white";
        node.FillColor = "darkCyan";
        label.Bold = true;
        node.Labels.Add(label);
        if (description != "") node.AddInfo = new Dictionary < string, object > {
            {
                "Description",
                description
            }
        };
        nodes.Add(node);
        return node;
    }
}
{% endhighlight %} 
{% endtabs %} 

![show tooltip when mouse hovers over any node](/aspnet/Diagram/Tooltip_images/Tooltip_img4.png)

### Disable tooltip at runtime

Tooltips on mouse over can be disabled by assigning `tooltip` property as `null`. The following code example illustrates how to disable the mouse over tooltip at runtime.

{% highlight js %}

    $("#diagram").ejDiagram({
        //Disables mouse over tooltip at runtime
        tooltip: null
    });

{% endhighlight %} 

## Tooltip for a specific node/connector

Tooltips can be customized for every node. Tooltip can be defined for individual node/connector by using the `Tooltip` property of that node/connector. In addition to that, you have to remove the **InheritTooltip** option from the `Constraints` of that node/connector. The following code example illustrates how to customize tooltips for individual elements.

{% tabs %}
{% highlight aspx-cs %}

        <!--Define tooltip template-->
        <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
            <span style="padding: 5px;"> {{"{{"}}:addInfo.Description{{}}}} </span>
        </div>
        </script>

 
        <%--   Initializes Diagram--%>
        <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" OnClientCreate="diagramCreate" Height="600px" Width="1000px" Locale="en-US" EnableContextMenu="true">
                 <Tooltip TemplateId="mouseovertooltip"></Tooltip>
        <PageSettings ScrollLimit="Diagram" />
        <SnapSettings SnapConstraints="None" />
     
    </ej:Diagram> 

{% endhighlight %}
{% highlight c# %}
public partial class DiagramFeatures: System.Web.UI.Page {
    protected void Page_Load(object sender, EventArgs e) {
        Node node = CreateNode(DiagramWebControl1.Nodes, "node1", 60, 60, 100, 100, "Elizabeth", "Managing Director");

    }

    private Node CreateNode(Collection nodes, String name, double width, double height, double offsetx, double offsety, string text = "", string description = "") {
        Node node = new Node();
        node.Name = name;
        node.Width = width;
        node.Height = height;
        node.OffsetX = offsetx;
        node.OffsetY = offsety;
        node.constraints = NodeConstraints.Default & ~NodeConstraints.InheritTooltip
        Label label = new Label();
        label.Text = text;
        label.FontColor = "white";
        node.FillColor = "darkCyan";
        label.Bold = true;
        node.Labels.Add(label);
        if (description != "") node.AddInfo = new Dictionary < string, object > {
            {
                "Description",
                description
            }
        };
        nodes.Add(node);
        return node;
    }
}
{% endhighlight %} 
{% endtabs %} 

## Tooltip alignments

### Tooltip relative to object

Diagram provides support to show tooltip around the node/connector that is hovered by mouse. You can align the tooltip as you wish by using the `Alignment` and `Margin` properties of tooltip. The `RelativeMode` property of tooltip defines whether the tooltip has to be displayed around the object or at the mouse position. The following code example illustrates how to position the tooltip around object.

{% tabs %}
{% highlight aspx-cs %}

        <!--Define tooltip template-->
        <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
            <span style="padding: 5px;"> {{"{{"}}:addInfo.Description{{}}}} </span>
        </div>
        </script>

 
        <%--   Initializes Diagram--%>
        <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" OnClientCreate="diagramCreate" Height="600px" Width="1000px" Locale="en-US" EnableContextMenu="true">
                 <Tooltip TemplateId="mouseovertooltip" RelativeMode="Object"></Tooltip>
        <PageSettings ScrollLimit="Diagram" />
        <SnapSettings SnapConstraints="None" />
     
    </ej:Diagram> 

{% endhighlight %}
{% highlight c# %}
public partial class DiagramFeatures: System.Web.UI.Page {
    protected void Page_Load(object sender, EventArgs e) {
        Node node = CreateNode(DiagramWebControl1.Nodes, "node1", 60, 60, 100, 100, "Elizabeth", "Director");

    }

    private Node CreateNode(Collection nodes, String name, double width, double height, double offsetx, double offsety, string text = "", string description = "") {
        Node node = new Node();
        node.Name = name;
        node.Width = width;
        node.Height = height;
        node.OffsetX = offsetx;
        node.OffsetY = offsety;
        Label label = new Label();
        label.Text = text;
        label.FontColor = "white";
        node.FillColor = "darkCyan";
        label.Bold = true;
        node.Labels.Add(label);
        if (description != "") node.AddInfo = new Dictionary < string, object > {
            {
                "Description",
                description
            }
        };
        nodes.Add(node);
        return node;
    }
}
{% endhighlight %} 
{% endtabs %} 

![position the tooltip around object](/aspnet/Diagram/Tooltip_images/Tooltip_img5.png)

### Tooltip relative to mouse position

To display the tooltip at mouse position, you need to set "Mouse" option to the `RelativeMode` property of tooltip. The following code example illustrates how to show tooltip at mouse position.

{% tabs %}
{% highlight aspx-cs %}

        <!--Define tooltip template-->
        <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
             <span style="padding: 5px;"> {{"{{"}}:addInfo.Description{{}}}} </span>
        </div>
        </script>

 
        <%--   Initializes Diagram--%>
        <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" OnClientCreate="diagramCreate" Height="600px" Width="1000px" Locale="en-US" EnableContextMenu="true">
                 <Tooltip TemplateId="mouseovertooltip" RelativeMode="Mouse"></Tooltip>
        <PageSettings ScrollLimit="Diagram" />
        <SnapSettings SnapConstraints="None" />
     
    </ej:Diagram> 

{% endhighlight %}
{% highlight c# %}
public partial class DiagramFeatures: System.Web.UI.Page {
    protected void Page_Load(object sender, EventArgs e) {
        Node node = CreateNode(DiagramWebControl1.Nodes, "node1", 60, 60, 100, 100, "Elizabeth", "Director");

    }

    private Node CreateNode(Collection nodes, String name, double width, double height, double offsetx, double offsety, string text = "", string description = "") {
        Node node = new Node();
        node.Name = name;
        node.Width = width;
        node.Height = height;
        node.OffsetX = offsetx;
        node.OffsetY = offsety;
        Label label = new Label();
        label.Text = text;
        label.FontColor = "white";
        node.FillColor = "darkCyan";
        label.Bold = true;
        node.Labels.Add(label);
        if (description != "") node.AddInfo = new Dictionary < string, object > {
            {
                "Description",
                description
            }
        };
        nodes.Add(node);
        return node;
    }
}
{% endhighlight %} 
{% endtabs %} 

![show tooltip at mouse position](/aspnet/Diagram/Tooltip_images/Tooltip_img6.png)


