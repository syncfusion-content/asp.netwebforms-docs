---
layout: post
title: Label | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to use Essential Diagram control Label's functionality and its behavior.
platform: aspnet
control: Diagram
documentation: ug
---

# Label

**Label** is a block of text that can be displayed over a node or connector. Label is used to textually represent an object with a string that can be edited at run time. You can add Multiple Labels to a node/connector.

## Create Label

You can add a label to a node/connector by defining the label object and adding that to the `Labels` collection of node/connector. The `Text` property of label defines the text to be displayed. The following code illustrates how to create a Label. 

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <%--Initializes labels collection--%>
               <labels>
                   <%-- Define the label text --%>
                   <ej:DiagramLabel Text="Label"></ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
       <Connectors>
           <ej:DiagramConnector>
               <sourcepoint x="200" y="50" />
               <targetpoint x="300" y="150" />
               <%--Initializes labels collection--%>
               <labels>
                   <%-- Define the label text --%>
                   <ej:DiagramLabel Text="Label" FillColor="white"></ej:DiagramLabel>
               </labels>
               <segments>
                   <ej:DiagramSegment Type="Orthogonal" Length="50" Direction="bottom"></ej:DiagramSegment>
               </segments>
           </ej:DiagramConnector>
       </Connectors>
    </ej:Diagram>

{% endhighlight %}

![Label Properties](/aspnet/Diagram/Label_images/Label_img1.png)

To explore more label properties, refer to [Label Properties](http://help.syncfusion.com/cr/aspnet/Syncfusion.JavaScript.DataVisualization.Models.Diagram.Label.html "Label Properties").

## Update Label at runtime

The client side API `updateLabel` is used to update the labels at run time.

The following code example illustrates how to change the label properties.

{% highlight js %}

var diagram = $("#diagram").ejDiagram("instance");
var selectedObject = diagram.model.selectedItems.children[0];
diagram.updateLabel(selectedObject.name, selectedObject.labels[0], { text: "label", fillColor: "red" });

{% endhighlight %}


## Alignment

Label can be aligned relative to the node boundaries. It has margin, offset, horizontal and vertical alignment settings. It is quite tricky when all four alignments are used together but gives you more control over alignment.

### Offset

The `Offset` property of label is used to align the labels based on fractions. 0 represents top/left corner, 1 represents bottom/right corner, and 0.5 represents half of width/height.

The following image shows the relationship between the label position (black colored circle) and offset (fraction values).

![Label Alignment](/aspnet/Diagram/Label_images/Label_img2.png)

### Horizontal and vertical alignments

The `HorizontalAlignment` property of label is used to set how the label is horizontally aligned at the label position determined from the fraction values. The `VerticalAlignment` property is used to set how label is vertically aligned at the label position. 

The following tables illustrates all the possible alignments visually with **offset (0, 0).**

| Horizontal Alignment | Vertical Alignment | Output with Offset(0,0) |
|---|---|---|
| Left | Top | ![Label Left Top Alignment](/aspnet/Diagram/Label_images/Label_img3.png) |
| Center | | ![Label Center alignment](/aspnet/Diagram/Label_images/Label_img4.png) |
| Right | | ![Label Right Alignment](/aspnet/Diagram/Label_images/Label_img5.png) |
| Left | Center | ![Label Left Center Alignment](/aspnet/Diagram/Label_images/Label_img6.png) |
| Center | | ![Label Center Alignment](/aspnet/Diagram/Label_images/Label_img7.png) |
| Right | | ![Label Right Alignment](/aspnet/Diagram/Label_images/Label_img8.png) |
| Left | Bottom | ![Label Left Bottom Alignment](/aspnet/Diagram/Label_images/Label_img9.png) |
| Center | | ![Label Center Alignment](/aspnet/Diagram/Label_images/Label_img10.png) |
| Right | | ![Label Right Alignment](/aspnet/Diagram/Label_images/Label_img11.png) |

The following codes illustrates how to align labels.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Align text and set label position --%>
                   <ej:DiagramLabel Text="Label"
                       HorizontalAlignment="Left" VerticalAlignment="Center" TextAlign="Center">
                       <Offset X="0" Y="0.5"/>
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>

{% endhighlight %}

![Label Alignment](/aspnet/Diagram/Label_images/Label_img12.png)

### Margin

**Margin** is an absolute value used to add some blank space in any one of its four sides. You can displace the labels with the `Margin` property.
The following code example illustrates how to align a label based on its `Offset`, `HorizontalAlignment`, `VerticalAlignment` and `Margin` values.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Set label margin --%>
                   <ej:DiagramLabel Text="Label"
                       HorizontalAlignment="Center" VerticalAlignment="Top" TextAlign="Center">
                       <Offset X="0.5" Y="1"/>
                       <Margin Top="10"/>
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>
        
{% endhighlight %}

![Margin](/aspnet/Diagram/Label_images/Label_img13.png)

### Text Alignment

The `TextAlign` property of label allows you to set how the text should be aligned (left, right, center, or justify) inside the text block. The following codes illustrate how to set textAlign for a label.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Set text align --%>
                   <ej:DiagramLabel Text="Text Align is set as Left" TextAlign="Left">                           
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>

{% endhighlight %}

![Text Alignment](/aspnet/Diagram/Label_images/Label_img14.png)

| TextAlign | Image |
|---|---|
| Left | ![Text Alignment Left](/aspnet/Diagram/Label_images/Label_img15.png) |
| Right | ![Text Alignment Right](/aspnet/Diagram/Label_images/Label_img16.png) |
| Center | ![Text Alignment Center](/aspnet/Diagram/Label_images/Label_img17.png) |
| Justify | ![Text Alignment Justify](/aspnet/Diagram/Label_images/Label_img18.png) |

## Wrapping

When text overflows node boundaries, you can control it by using text wrapping. So, it is wrapped into multiple lines. The `Wrapping` property of label defines how the text should be wrapped. The following code illustrates how to wrap a text in a node.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Wrap label text --%>
                   <ej:DiagramLabel Text= "Text - Wrapping" WrapText="true" FontSize="14">                           
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>

{% endhighlight %}

![Text Wrapping](/aspnet/Diagram/Label_images/Label_img19.png)

| Values | Description | Image |
|---|---|---|
| NoWrap | Text will not be wrapped | ![Text with NoWrap](/aspnet/Diagram/Label_images/Label_img20.png) |
| Wrap | Text-wrapping occurs when the text overflows beyond the available node width. | ![Text with Wrap](/aspnet/Diagram/Label_images/Label_img21.png) |
| WrapWithOverflow (Default) | Text-wrapping occurs when the text overflows beyond the available node width. However, the text may overflow beyond the node width in the case of a very long word. | ![Text with WrapWithOverflow](/aspnet/Diagram/Label_images/Label_img22.png) |

## Appearance

You can change the font style of the labels with the font specific properties(`FontSize`,`FontFamily`,`FontColor`.,). The following code illustrates how to customize the appearance of a label.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Change label appearance --%>
                   <ej:DiagramLabel Text= "Label Text" 
                       FontFamily="TimesNewRoman" FontSize="12" FontColor="Black" 
                       Bold="true" Italic="true" 
                       TextDecoration="Underline">                           
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>

{% endhighlight %}

![Text Appearance](/aspnet/Diagram/Label_images/Label_img23.png)

The fill and border appearances of the text can also be customized with appearance specific properties of label.The following code illustrates how to customize background and border of a label.

{% highlight aspx-cs %}

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
       <Nodes>
           <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
               <labels>
                   <%-- Change label appearance --%>
                   <ej:DiagramLabel Text="Label Text" 
                       FillColor="white" BorderColor="Black" BorderWidth="1">                           
                   </ej:DiagramLabel>
               </labels>
           </ej:BasicShape>
       </Nodes>
   </ej:Diagram>
{% endhighlight %}

![Text Appearance Customize](/aspnet/Diagram/Label_images/Label_img24.png)

## Drag

A **Label** can be displaced from its original position to any preferred location interactively. Dragging is disabled by default. You can enable label dragging with the `Constraints` property of node/connector. The following code illustrates how to enable label **dragging**.

{% highlight aspx-cs %}

        <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px">
            <%--    Add the node to the nodes collection --%>
            <Nodes>
                <%--Defines nodes--%>
                <ej:BasicShape Name="task1" OffsetX="100" OffsetY="100" Height="100" Width="100" FillColor="#1BA0E2" BorderColor="black" Constraints="Default , DragLabel">
                    <labels>
                    <ej:DiagramLabel Name="task1" Text="Label" FontColor="White"></ej:DiagramLabel>
                </labels>
                </ej:BasicShape>

            </Nodes>
            <Connectors>
                <ej:DiagramConnector>
                    <sourcepoint x="200" y="50"></sourcepoint>
                    <targetpoint x="300" y="150"> </targetpoint>
                </ej:DiagramConnector>
            </Connectors>
        </ej:Diagram>

{% endhighlight %}

![Text Dragging](/aspnet/Diagram/Label_images/Label_img25.png)

## Rotate

You can rotate the labels to any desired angle. Labels are rotated to the angle that is defined by the `RotateAngle` property of label. The following code illustrates how to rotate a label.

{% highlight aspx-cs %}

     <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
         <Nodes>
             <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
                 <labels>
                     <%-- Rotate text --%>
                     <ej:DiagramLabel Text="Label" RotateAngle="45">                           
                     </ej:DiagramLabel>
                 </labels>
             </ej:BasicShape>
         </Nodes>
     </ej:Diagram>

{% endhighlight %}

![Text Rotate](/aspnet/Diagram/Label_images/Label_img26.png)

N> There is no built-in support to rotate labels interactively.

## Edit

**Diagram** provides support to edit a Label at runtime, either programmatically or interactively. By default, label is in **View** mode. But it can be brought to edit mode in two ways; 

1. By double-clicking the label.
2. By selecting the item and pressing the **F2** key. 

Double-clicking any label will enables **editing** of that. Double-clicking the node enables first label editing. When the focus of editor is lost, the label for the node is updated.

You can programmatically edit the label by changing the `Mode` of the label. The following code illustrates how to edit the label programmatically.

{% highlight js %}

var diagram = $("#diagram").ejDiagram("instance");
var node = diagram.model.selectedItems.children[0];
//Sets label mode as Edit 
var options = {
	mode: ej.datavisualization.Diagram.LabelEditMode.Edit
};
diagram.updateLabel(node.name, node.labels[0], options);

{% endhighlight %}

![Text Edit](/aspnet/Diagram/Label_images/Label_img27.png)

### Read Only labels

Diagram allows to create read only labels. You have to set the `ReadOnly` property of label to enable/disable the read only mode. The following code illustrates how to enable **readOnly** mode.

{% highlight aspx-cs %}

     <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
         <Nodes>
             <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
                 <labels>
                     <%-- Rotate text --%>
                     <ej:DiagramLabel Text="Label" ReadOnly="true">                           
                     </ej:DiagramLabel>
                 </labels>
             </ej:BasicShape>
         </Nodes>
     </ej:Diagram>

{% endhighlight %}

### Drag Limit

Diagram label dragging can be restricted by enabling/disabling `DragLimit` constraints of the connectors. Also we can define the drag limit in all direction using `DragLimit` property of the connector. Drag limit only applicable for connector labels.

{% highlight aspx-cs %}

    <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" Height="600px" Width="100%" EnableContextMenu="false">
        <Connectors>
        <%-- Enable DragLimit constraints to the connector --%>
            <ej:DiagramConnector Name="Connector3" Constraints="Default, DragLabel, DragLimit"></ej:DiagramConnector>
                <labels>
                     <ej:DiagramLabel>
                     <%-- Defines the drag limit property in all direction --%>
                       <Draglimit Left="30" Top="30" Right="30" Bottom="30">
                      </Draglimit>
                    </ej:DiagramLabel>
                </labels>
        </Connectors>
    </ej:Diagram>

{% endhighlight %}

## Multiple labels

You can add any number of labels to a node or connector. The following code illustrates how to add multiple labels to a node. 

{% highlight aspx-cs %}

     <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px">
         <Nodes>
             <ej:BasicShape Width="100" Height="100" OffsetX="100" OffsetY="100" FillColor="#1BA0E2" BorderColor="black">
                 <labels>
                     <%-- Add multiple labels --%>
                     <ej:DiagramLabel Text="Left">
                         <Offset X="0.12" Y="0.1"></Offset>
                     </ej:DiagramLabel>
                     <ej:DiagramLabel Text="Center">
                         <Offset X="0.5" Y="0.5"></Offset>
                     </ej:DiagramLabel>
                      <ej:DiagramLabel Text="Right">
                         <Offset X="0.82" Y="0.9"></Offset>
                     </ej:DiagramLabel>
                 </labels>
             </ej:BasicShape>
         </Nodes>
     </ej:Diagram>

{% endhighlight %}

![Multiple Label](/aspnet/Diagram/Label_images/Label_img28.png)

## Limitation

* To enable faster rendering, labels are rendered in a separate layer because of this, all the labels always stay on top. When two nodes are overlapped, text of underlying node is not hidden by the overlapped node. 

| Expected behavior | Current behavior |
|---|---|
| ![Expected behavior](/aspnet/Diagram/Label_images/Label_img29.png) | ![Current behavior](/aspnet/Diagram/Label_images/Label_img30.png) |
