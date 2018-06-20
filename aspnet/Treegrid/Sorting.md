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

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlSorting"

             AllowSorting="true">



</ej:TreeGrid>

{% endhighlight %}



### Multicolumn sorting

TreeGrid allows you to sort multiple columns by clicking the desired column headers while holding the CTRL key. The following code example shows you how to enable Multicolumn sorting in TreeGrid control.


{% highlight html %}

   <ej:TreeGrid runat="server" ID="TreeGridControlSorting"

             AllowSorting="true"

             AllowMultiSorting="true">

    </ej:TreeGrid>

{% endhighlight %}



The following screenshot shows the output of Multicolumn sorting in TreeGrid control.



 ![](Sorting_images/Sorting_img1.png) 





