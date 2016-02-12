---
layout: post
title: Define and add the frequently used nodes/connectors to the symbol palette
description: How to add shapes to the symbol palette and drag and drop them over the drawing area?
platform: aspnet
control: Diagram
documentation: ug
---

# Symbol Palette

The **SymbolPalette** displays a collection of palettes. The Palette shows a set of nodes and connectors. It allows you to drag and drop the nodes and connectors into the Diagram. 

## Palettes
 
A palette allows to display a group of related symbols and it textually annotates the group with its header.
To initialize a palette, define a palette object with the property `Name` that is displayed as the header text of palette. The `Expanded` property of palette allows to expand/collapse its palette items. 
You can add any number of palettes to the `Palettes` collection of the symbol palette.
The following code example illustrates how to define a palette and how its added to symbol palette.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <%--define a palette with its name and expands its children.--%>
            <ej:DiagramPalette Name="Basic Shapes" Expanded="true"></ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

The following image shows the symbol palette with multiple palette Items.

![](/aspnet/Diagram/Symbol-Palette_images/Symbol-Palette_img3.png)

### Palette Items

The palette items need to be defined and added to the `Items` collection of the palette. You can create a palette item as a node, group, connector, lane, or phase except swimlane. To create a palette item, you first need to define that element as JSON. The following code example illustrates how to define a palette item.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <%--define a palette with its name and expands its children.--%>
            <ej:DiagramPalette Name="Basic Shapes" Expanded="true">
                <Items>
                    <%--define a node with its size, position and shape.--%>
                    <ej:BasicShape Width="40" Height="40" OffsetX="20" Name="Ellipse" 
                        OffsetY="20" Shape="Ellipse">
                    </ej:BasicShape>
                </Items>
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

Note : You can add any item to palette such as node, connector, group, lane, phase except swimlane.

{% endhighlight %}  

#### Customize the size of palette items

You can customize the size of the individual palette items. The `PaletteItem` property of node enables you to define the size of the symbol items. The following code example illustrates how to change the size of a palette item.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <ej:DiagramPalette Name="Basic Shapes" Expanded="true">
                <Items>
                    <ej:BasicShape Width="40" Height="80" Name="Rectangle">
                        <%--Specifies the size of palette Item--%>
                        <PaletteItem Width="50" Height="50">
                            <Margin Left="20" Top="20" Right="20" Bottom="20">
                            </Margin>
                        </PaletteItem>
                    </ej:BasicShape>
                </Items>
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

Palette item size is set based on the precedence flow given in the following table.

| Palette Item | Rendering Size |  
|---|---|---|
| Precedence - Width | paletteItem.width > model.paletteItemWidth > node.width |  
| Precedence - Height | paletteItem.height > model.paletteItem.Height > node.height |  

Palette item size can be based on the actual size of the node, regardless of the precedence. 

#### Stretch the shape in to the Palette Item

The `enableScale` property of the palette item enables you to customize the size of the item regardless of the precedence. The following code example illustrates how to customize the palette item size.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <%--define a palette with its name and expands its children.--%>
            <ej:DiagramPalette Name="Basic Shapes" Expanded="true">
                <Items>
                    <ej:BasicShape Width="40" Height="80" Name="Rectangle">
                        <%--Enables to fit the content into the specified palette item size--%>
                        <PaletteItem EnableScale="true">
                        </PaletteItem>
                        <%--When it is set as false, the element is rendered with actual node size--%>
                    </ej:BasicShape>
                </Items>
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

![](/aspnet/Diagram/Symbol-Palette_images/Symbol-Palette_img1.png)

![](/aspnet/Diagram/Symbol-Palette_images/Symbol-Palette_img2.png)


### Palette header 

Palette headers are often used to display unit of information that proceeds the information about the palette. By default, the header content is the name of the palette by default, so when you customize the header of the palette, it will update on all the palette as well.

Following code example illustrates how to define default palette header.


{% highlight C# %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <%--Defines the default header--%>
            <ej:DiagramPalette Name="Basic Shapes" Expanded="true">
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}


![](/aspnet/Diagram/Symbol-Palette_images/Symbol-Palette_img7.png)

#### Customize the Palette Header

Palettes can be annotated with its header texts. Following code example illustrates how to define palette header.

Also, you can embed any Html element into a palette header by defining the ScriptTemplate id to palette's `TemplateId` property. Following code example illustrates how to customize palette headers.

{% highlight ASPX %}


    &lt;!--dependency scripts--&gt;
        &lt;script id="svgTemplate" type="text/x-jsrender"&gt;
        &lt;!--  define html element --&gt;
            &lt;svg version="1.0" xmlns="http://www.w3.org/2000/svg" width="225px" height="28px"&gt;
                &lt;g visibility="visible"&gt;
                    &lt;image width="26px" height="26px" opacity="1" xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="image.png"&gt;&lt;/image&gt;
                    &lt;text x="40" y="18" font-size="14"&gt;
                        <tspan>Basic Shapes</tspan>
                    &lt;/text&gt;
                &lt;/g&gt;
            &lt;/svg&gt;
        &lt;/script&gt;												


{% endhighlight %}


{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <Palettes>
            <%--Create a palette with custom header and set the id of the script template--%>
            <ej:DiagramPalette Name="Basic Shapes" TemplateId="svgTemplate">
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

The following image shows the customized palette header

![](/aspnet/Diagram/Symbol-Palette_images/customizethepaletteheader_img1.png)

## Symbol Previews

Image, simple snippet to customize the preview size

You can customize the preview size of the individual palette items. The `PaletteItem` property of node enables you to define the preview size of the symbol items. The following code example illustrates how to change the preview size of a palette item.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" DiagramId="DiagramContent"  runat="server">
        <Palettes>
            <ej:DiagramPalette Name="Basic Shapes">
                <Items>
                    <ej:BasicShape Width="50" Height="50" Name="Rectangle">
                        <%--Specifies the individual palette item preview size--%>
                        <PaletteItem PreviewHeight="100" PreviewWidth="100">
                        </PaletteItem>
                    </ej:BasicShape>
                </Items>
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

![](/aspnet/Diagram/Symbol-Palette_images/customizethepaletteheader_img5.png)

You can also customize the preview size of the all palette items. The `PreviewWidth` and `PreviewHeight` property of SymbolPalette enables you to define the preview size to all the symbol palette items. The following code example illustrates how to change the preview size of a symbol palette items.

{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" DiagramId="DiagramContent"
        PreviewWidth="100" PreviewHeight="100" runat="server"><%--Specifies the preview size to symbol palette items. --%>
        <%--Defines the palette collection--%>
        <Palettes>
            <ej:DiagramPalette Name="Basic Shapes">
                <Items>
                    <ej:BasicShape Width="50" Height="50" Name="Rectangle" Shape="Rectangle">
                    </ej:BasicShape>
                </Items>
            </ej:DiagramPalette>
        </Palettes>
    </ej:SymbolPalette>

{% endhighlight %}

![](/aspnet/Diagram/Symbol-Palette_images/customizethepaletteheader_img4.png)

Symbol palette allows to sets the offset of the dragging helper relative to the mouse cursor.


{% highlight ASPX %}

    <ej:SymbolPalette ID="symbolpalette" Width="100%" Height="100%" runat="server">
        <%--Specifies the offset of the dragging helper relative to the mouse cursor.--%>
        <PreviewOffset X="50" Y="50" />
    </ej:SymbolPalette>

{% endhighlight %}

![](/aspnet/Diagram/Symbol-Palette_images/customizethepaletteheader_img5.png)


preview size is set based on the precedence flow given in the following table.

| Palette Item |   Preview Size |
|---|---|---|
| Precedence - Width |  paletteItem.previewWidth > model.previewWidth > node.width |
| Precedence - Height | paletteItem.previewHeight > model.previewHeight > node.height |

Preview item size can be based on the actual size of the node, regardless of the precedence.


## Appearance 

You can show/hide the palette item texts by using the `ShowPaletteItemText` property of symbol palette and you can change the height of palette header by using `HeaderHeight` property of symbol palette. The following code illustrates how to customize the appearance of the symbol Palette.

{% highlight C# %}

    <%--Specifies whether palette item text should be visible or not and height of the symbol palette header.--%>
    <ej:SymbolPalette ID="symbolPalette" Width="100%" Height="100%"
        ShowPaletteItemText="true" HeaderHeight="30"> 
    </ej:SymbolPalette>

{% endhighlight %}
