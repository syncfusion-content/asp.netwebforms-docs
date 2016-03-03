---
layout: post
title: Show tooltips when mouse hovers over objects
description: How to show/hide tooltips when mouse hovers over objects or during interaction?
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
| ![](/aspnet/Diagram/Tooltip_images/Tooltip_img1.png) | ![](/aspnet/Diagram/Tooltip_images/Tooltip_img2.png) | ![](/aspnet/Diagram/Tooltip_images/Tooltip_img3.png) |

### Disable default tooltip

To disable the default tooltip, You need to set `SelectedItems.Tooltip` as `null`. The following code example illustrates how to disable default tooltip.

{% tabs %}
{% highlight ASPX %}

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

 {% highlight ASPX %}

        <!--Define tooltip template-->
        <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
            <span style="padding: 5px;"> {{:name}} </span>
        </div>
        </script>

 
        <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px" Tool="SingleSelect">
            <%--    Add the node to the nodes collection --%>
            <Nodes>
                <%--Defines nodes--%>
                <ej:BasicShape Name="Elizabeth" OffsetX="100" OffsetY="100" Height="40" Width="70" FillColor="darkCyan" BorderColor="black">
                    <labels>
                        <ej:DiagramLabel Text="Elizabeth"  FontColor = "white" Bold = true></ej:DiagramLabel>
                    </labels>
                </ej:BasicShape>
            </Nodes>
            <%--Defines mouse over tooltip--%>
            <Tooltip TemplateId="mouseovertooltip">
                <Alignment Horizontal="Center" Vertical="Center"></Alignment>
            </Tooltip>
        </ej:Diagram>
        
{% endhighlight %} 

![](/aspnet/Diagram/Tooltip_images/Tooltip_img4.png)

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

{% highlight ASPX %}

            <Nodes>
                <%--Defines nodes--%>
                <ej:BasicShape Name="Elizabeth" OffsetX="100" OffsetY="100" Height="40" Width="70" FillColor="darkCyan" BorderColor="black" Constraints="InheritTooltip">
                    <Tooltip TemplateId="nodetooltiptemplate">
                        </Tooltip>
                    <labels>
                        <ej:DiagramLabel Text="Elizabeth"  FontColor = "white" Bold = true></ej:DiagramLabel>
                    </labels>
                </ej:BasicShape>
            </Nodes>

{% endhighlight %} 

## Tooltip alignments

### Tooltip relative to object

Diagram provides support to show tooltip around the node/connector that is hovered by mouse. You can align the tooltip as you wish by using the `Alignment` and `Margin` properties of tooltip. The `RelativeMode` property of tooltip defines whether the tooltip has to be displayed around the object or at the mouse position. The following code example illustrates how to position the tooltip around object.

{% tabs %}

{% highlight ASPX %}

    <!--Define tooltip template-->
    <script type="text/x-jsrender" id="mouseovertooltip">
        <div style="background-color: #F08080; color: white; white-space: nowrap; height: 20px">
            <span style="padding: 5px;"> {{:addInfo.Designation}} </span>
        </div>
    </script>

 

    <Nodes>
                <%--Defines nodes--%>
                <ej:BasicShape Name="Director" OffsetX="100" OffsetY="100" Height="40" Width="70" FillColor="darkCyan" BorderColor="black" Constraints="InheritTooltip">
                    <Tooltip TemplateId="nodetooltiptemplate" RelativeMode="Object">
                          <Alignment Horizontal="Center" Vertical="Top"></Alignment>
                        </Tooltip>
                    <labels>
                        <ej:DiagramLabel Text="Elizabeth"  FontColor = "white" Bold = true></ej:DiagramLabel>
                    </labels>
                </ej:BasicShape>
            </Nodes>
            
{% endhighlight %}

{% endtabs %}

![](/aspnet/Diagram/Tooltip_images/Tooltip_img5.png)

### Tooltip relative to mouse position

To display the tooltip at mouse position, you need to set "Mouse" option to the `RelativeMode` property of tooltip. The following code example illustrates how to show tooltip at mouse position.

{% highlight ASPX %}

     <%--    Add the node to the nodes collection --%>
            <Nodes>
                <%--Defines nodes--%>
                <ej:BasicShape Name="Director" OffsetX="100" OffsetY="100" Height="40" Width="70" FillColor="darkCyan" BorderColor="black" Constraints="InheritTooltip">
                    <Tooltip TemplateId="nodetooltiptemplate" RelativeMode="Mouse">
                          <Alignment Horizontal="Center" Vertical="Top"></Alignment> 
                        </Tooltip>
                    <labels>
                        <ej:DiagramLabel Text="Elizabeth"  FontColor = "white" Bold = true></ej:DiagramLabel>
                    </labels>
                </ej:BasicShape>
            </Nodes>


{% endhighlight %}

![](/aspnet/Diagram/Tooltip_images/Tooltip_img6.png)


