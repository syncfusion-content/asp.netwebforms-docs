---
layout: post
title: User Interaction
description: user interaction
platform: js
control: TreeMap
documentation: ug
---

# User Interaction

You can interact with the **TreeMap** control by selecting either the leaf nodes or the groups.

## Selection

Selection support enables you to highlight the items where the mouse tapping has occurred. You can select the following contents of the **TreeMap** control:

* Leaf Nodes
* Group

### Single Selection

To enable the selection of leaf nodes, the `HighlightOnSelection` property in `treemap` is set as **true**. When selection occurs, the item is highlighted with a bounding rectangle around the selected leaf node.
The border can be customized with `HighlightBorderBrush` and `HighlightBorderThickness` properties.


{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" HighlightOnSelection = "true" HighlightBorderBrush = "#3e3e3e" HighlightBorderThickness = "1">
        // ...
</ej:Treemap>

{% endhighlight %}

![](User-Interaction_images/User-Interaction_img1.png)

### Group Selection

To enable the selection of leaf nodes, the `HighlightGroupOnSelection` property in `treemap` is set as **true**. When selection occurs, bounding rectangle highlights the selected group.

{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" HighlightGroupOnSelection = "true" HighlightBorderBrush = "#3e3e3e" HighlightBorderThickness = "1">
        // ...
</ej:Treemap>
        
{% endhighlight %}
        
![](User-Interaction_images/User-Interaction_img3.png)

## MultiSelection

This feature enables you to select multiple leaf nodes or groups simultaneously. To enable this feature for leaf nodes, use `ItemSelectionMode` as "**multiple**" and for groups, use `GroupSelectionMode` as "**multiple**"
To select multiple items simultaneously, the mouse tap should be done along with a continuous press of "**Control**" key.  

##### Selection (Multiple)

{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" ItemSelectionMode = "Multiple" HighlightOnSelection = "true" HighlightBorderBrush = "#3e3e3e" HighlightBorderThickness = "1">
        // ...
</ej:Treemap>
        
{% endhighlight %}

![](User-Interaction_images/User-Interaction_img2.png)

#### Group Selection (Multiple)

{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" GroupSelectionMode = "Multiple" HighlightGroupOnSelection = "true" HighlightBorderBrush = "#3e3e3e" HighlightBorderThickness = "1">
        // ...
</ej:Treemap>
        
{% endhighlight %}

![](User-Interaction_images/User-Interaction_img4.png)

## Drag On Selection

This feature enables you to highlight/select the leaf nodes or groups by the dragging the mouse pointer over the **TreeMap** items.

### Dragging On Selection

To enable this feature, you have to set `DraggingOnSelection` as "**true**".

{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" DraggingOnSelection = "true">
        // ...
</ej:Treemap>
        
{% endhighlight %}

![](User-Interaction_images/User-Interaction_img5.png)

### Dragging Group On Selection

To enable this feature, you have to set `DraggingGroupOnSelection` as "**true**".

{% highlight js %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth" DraggingGroupOnSelection = "true">
        // ...
</ej:Treemap>
        
{% endhighlight %}

![](User-Interaction_images/User-Interaction_img6.png)