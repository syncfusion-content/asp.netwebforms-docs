---
layout: post
title: Ruler is used to measure the distance of nodes and connectors from origin of the page.
description:  how to measure the distance of Nodes and Connectors?
platform: aspnet
control: Diagram
documentation: ug
---

# Rulers

The Ruler provides a Horizontal and Vertical guide for measuring in the Diagram control. The Ruler can be used to measure the Diagram objects, indicate positions, and align Diagram elements. This is especially useful in creating scale models. 

## Adding Rulers to the Diagram
Use the following code example to add the ruler to the Diagram.


{% highlight aspx-cs %}

<ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" Height="600px" Width="100%" EnableContextMenu="false">
         <RulerSettings ShowRulers="true">
        </RulerSettings>
</ej:Diagram>

{% endhighlight %}



![](/aspnet/Diagram/Rulers_images/Rulers_images1.png)

## Customizing the Ruler

By default, ruler segments are arranged based on measurement units.

Segment width, the textual description of the ruler segment, and the appearance of the ruler ticks can be customized. Use the following code example to customize the ruler.

{% tabs %} 
{% highlight aspx-cs %}

    <ej:Diagram ClientIDMode="Static" ID="DiagramWebControl1" runat="server" Height="600px" Width="100%" EnableContextMenu="false">
            <RulerSettings ShowRulers="true">
                <HorizontalRuler ArrangeTick="arrangeTick" SegmentWidth="100" Interval="6" TickAlignment="LeftOrTop" Thickness="25" MarkerColor="red" />
                <VerticalRuler ArrangeTick="arrangeTick" SegmentWidth="100" Interval="6" TickAlignment="LeftOrTop" Thickness="25" MarkerColor="red" />
            </RulerSettings>
    </ej:Diagram>

{% endhighlight %}

{% highlight js %} 

    function arrangeTick(args) {
        // Customizing the Ruler ticks.
        if (args.tickInterval % 100 == 0) {
        }
        else if (args.tickInterval % 50 == 0) {
            args.tickLength = 12.5
        }
    }

{% endhighlight %}
{% endtabs %}

![](/aspnet/Diagram/Rulers_images/Rulers_images2.png)

