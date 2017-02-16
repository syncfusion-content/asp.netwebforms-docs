---
layout: post
title:  ToolTip | PivotGrid | ASP.NET | Syncfusion 
description: ToolTip
platform: aspnet
control: PivotGrid
documentation: ug
---

# ToolTip

Allows you to display the details of the cell on hovering value cells. By default, tooltip is enabled.  You can disable tooltip in PivotGrid by setting the `enableToolTip` property to false.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableToolTip="false">
 </ej:PivotGrid>

{% endhighlight %}


## ToolTip Animation

The PivotGrid provides option to animate tooltip displayed in the grid.  The animation enhances the appearance of tooltip by displaying it slowly.  You can enable animation in tooltip by setting `EnableToolTipAnimation` property to true.


{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableToolTipAnimation="false">
 </ej:PivotGrid>

{% endhighlight %}

![](ToolTip_images/ToolTip.png)

