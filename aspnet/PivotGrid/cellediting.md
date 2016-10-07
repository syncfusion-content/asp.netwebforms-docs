---
layout: post
title: Cell-Editing | PivotGrid | ASP.NET | Syncfusion 
description: cell editing
platform: aspnet
control: PivotGrid
documentation: ug
---

# Cell Editing

I> This feature is applicable only for Relational data source.

Cell editing allows you to edit and alter the values in PivotGrid. The summary values will be recreated based on the edited values. By selecting multiple cells (like in cell selection feature), you can edit multiple cells at the same time.
  
You can enable cell editing option in PivotGrid by setting the `EnableCellEditing` property to true.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" EnableCellEditing="true" runat="server" ClientIDMode="Static">
    //...
</ej:PivotGrid>

{% endhighlight %}

![](Cell-Editing_images/celleditingclient.png)


