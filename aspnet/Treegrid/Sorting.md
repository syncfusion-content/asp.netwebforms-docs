---
layout: post
title: Sorting | TreeGrid | ASP.NET | Syncfusion
description: sorting
platform: aspnet
control: TreeGrid
documentation: ug
---

# Sorting

The TreeGrid control has built-in support for Sorting one or more columns.

### Sorting Columns

TreeGrid allows the items to be sorted in ascending or descending order based on the selected column by enabling the AllowSorting option in TreeGrid control. The following code example shows you how to enable Sorting in TreeGrid control.

The following code example shows you how to enable Sorting in TreeGrid control.
{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlSorting"
             AllowSorting="true">
</ej:TreeGrid>

{% endhighlight %}

### Multicolumn sorting

TreeGrid allows you to sort multiple columns by clicking the desired column headers while holding the **CTRL** key. The following code example shows you how to enable Multicolumn sorting in TreeGrid control.


{% highlight html %}

   <ej:TreeGrid runat="server" ID="TreeGridControlSorting"
             AllowSorting="true"
             AllowMultiSorting="true">
    </ej:TreeGrid>

{% endhighlight %}

The following screenshot shows the output of Multicolumn sorting in TreeGrid control.

 ![](Sorting_images/Sorting_img1.png) 

## Disable sorting for specific column

It is possible to disable sorting for a specific column by setting `AllowSorting` as `false` in the column definition.

The below code snippet demonstrates this.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlSorting"
             AllowSorting="true">
    <Columns>
    <ej:TreeGridColumn Field="taskName" HeaderText="Task Name" AllowSorting="true"></ej:TreeGridColumn>
    </Columns>
    </ej:TreeGrid> 
   
{% endhighlight %}

## Sort column at initial load

In TreeGrid, It is possible to render the control with sorted columns, this can be achieve by `SortedColumns` property and it was defined with `Field` and `Direction` properties.

The following code shows how to add sorted column in TreeGrid.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlSorting"
             AllowSorting="true">
    <SortedColumns >
        <ej:TreeGridSortedColumn Direction="Descending" Field="taskName" />
    </SortedColumns>
</ej:TreeGrid>
   
{% endhighlight %}

![](Sorting_images/Sorting_img2.png)

The above screenshot shows TreeGrid rendered with descending order of **Task Name** column.
{:.caption}



