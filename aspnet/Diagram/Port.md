---
layout: post
title: Ports | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to draw/create connections between the nodes with specific points.
platform: aspnet
control: Diagram
documentation: ug
---

# Port

Essential Diagram for ASP.NET provides support to define custom ports for making connections.

![connections between the nodes with multiple ports](/aspnet/Diagram/Port_images/Port_img3.png)

When a connector is connected between two nodes, its end points are automatically docked to node's nearest boundary as shown in the following image. 

![connector is connected between ports of two nodes](/aspnet/Diagram/Port_images/Port_img4.png)

Ports act as the connection points of node and allows to create connections with only those specific points as shown in the following image.

![Ports act as the connection points of node](/aspnet/Diagram/Port_images/Port_img5.png)

## Create Port

### Add ports when initializing nodes

To add a connection port, you need to define the port object and add it to node's `Ports` collection. The `Offset` property of port accepts an object of fractions and used to determine the position of ports. The following code illustrates how to add ports when initializing the node.

{% highlight aspx-cs %}

        <%--  To Create a port  --%>
        <ej:Diagram ID="Diagram" runat="server" Height="400px" Width="400px">
            <Nodes>
                <ej:BasicShape Name="node1" OffsetX="100" OffsetY="100" BorderColor="black" BorderWidth="2" FillColor="darkcyan">
                    <%-- Adding the ports to the ports collection --%>
                    <Ports>
                        <ej:DiagramPort Name="port1" Visibility="Visible">
                            <%-- Specifies the offset of the port --%>
                            <ej:Offset X="0" Y=".5"></ej:Offset>
                        </ej:DiagramPort>
                    </Ports>
                </ej:BasicShape>
            </Nodes>
        </ej:Diagram>

{% endhighlight %} 

### Add ports at runtime

You can add ports at runtime by using the client side method `addPorts`. The following code illustrates how to add ports to node at runtime.

{% highlight js %}

    // Defines a collection of ports that have to be added at runtime
    var ports = [
        {
            name: "port1",
            // Specifies the port offset – fraction value relative
            to node bounds – determines the position of port on node
            offset: {	
                x: 0,	
                y: 0.5
            }
        },
        { name: "port2",offset: {x: 1,y: 0.5 }},
        { name: "port3",offset: {x: 0.5,y: 0 }},
        { name: "port4",offset: {x: 0.5,y: 1 }}
    ];

    // Gets the instance for the Diagram
    var diagram = $("#diagram").ejDiagram("instance");
    // Adds the ports to the node of name "node"
    diagram.addPorts("node", ports)

{% endhighlight %}

![add ports to node at runtime](/aspnet/Diagram/Port_images/Port_img1.png)

To explore the set of properties for defining a port, refer to [Port Properties](http://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Port.html  "Port Properties")

### Update Port at runtime

The client side API `updatePort` is used to update the ports at run time. The following code example illustrates how to change the port properties.

{% highlight js %}

    var diagram = $("#diagram").ejDiagram("instance");
    var selectedObject = diagram.model.selectedItems.children[0];
    var visibility = ej.datavisualization.Diagram.PortVisibility.Visible;
    diagram.updatePort(selectedObject.name, selectedObject.ports[0], { fillColor: "red", visibility: visibility });

{% endhighlight %}

## Connect with ports

Connector’s `SourcePort` and `TargetPort` properties allow to create connections between some specific points of source/target nodes. 
For more information about creating connections with port, refer to [Connections with ports](/aspnet/Diagram/Connector#connections-with-ports "Connections with ports")

## Appearance 

You can change the shape of port by using its `Shape` property. To explore the different types of port shapes, refer to [Port Shapes](https://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Port.html#Syncfusion_JavaScript_DataVisualization_Models_Diagram_Port_Shape "Port Shapes").
The appearance of ports can be customized with a set of style specific properties. 

The following code illustrates how to change the appearance of port.

{% highlight aspx-cs %}
         
        <ej:Diagram ID="Diagram" runat="server" Height="400px" Width="400px">
            <Nodes>
                <ej:BasicShape Name="node1" OffsetX="100" OffsetY="100" BorderColor="black" BorderWidth="2" FillColor="darkcyan">
                    <%-- Adding the ports to the ports collection --%>
                    <ports>
                        <%--Customizes the appearance and Defines the shape of port--%>
                        <ej:DiagramPort Name="port1" Visibility="Visible" Shape="Circle" FillColor="yellow" Size="12" BorderColor="black" BorderWidth="2">
                            <%-- Specifies the port position --%>
                            <ej:Offset X="1" Y=".5"></ej:Offset>
                        </ej:DiagramPort>
                    </ports>
                </ej:BasicShape>
            </Nodes>
        </ej:Diagram>

{% endhighlight %}

![change the appearance of port](/aspnet/Diagram/Port_images/Port_img2.png)

## Constraints

The `Constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/aspnet/Diagram/Constraints#portconstraints)