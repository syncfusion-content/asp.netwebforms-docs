---
layout: post
title: Toolbar
description: toolbar
platform: aspnet
control: TreeGrid
documentation: ug
---

# Toolbar

TreeGrid control contains toolbar options for adding, deleting and editing the records. You can customize the TreeGrid Toolbar tools by using ToolbarSettings API. 

In TreeGrid by using RowPosition API, the index position for the newly added row can be provided. Default value of the RowPosition property is top. The Enum values for RowPosition API are,

* top
* bottom
* aboveSelectedRow
* belowSelectedRow

You can enable toolbar for TreeGrid, using the following code example.





{% highlight html %}

<ej:TreeGrid ID="TreeGridControlEditing" runat="server">//..



      <EditSettings RowPosition="aboveSelectedRow"/>



      <ToolbarSettings ShowToolbar="true"



               ToolbarItems="add,edit,delete,update,cancel,collapseAll,expandAll"/>



</ej:TreeGrid>



{% endhighlight %}



The following screenshot displays the toolbar option in TreeGrid control

![](Toolbar_images/Toolbar_img1.png) 
{:.image }


