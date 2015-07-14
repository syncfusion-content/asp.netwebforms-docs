---
layout: post
title: Editing
description: editing
platform: aspnet
control: TreeGrid
documentation: ug
---

## Editing

The TreeGrid control provides built-in support for Editing cell items. 

Cell Editing

Update the task details through grid Cell Editing by setting EditMode as CellEditing.

The following code example shows you how to enable CellEditing in TreeGrid control.







{% highlight html %}



<ej:TreeGrid runat="server" ID="TreeGridControlEditing">

//...

<EditSettings AllowEditing="true" EditMode="CellEditing"/>

</ej:TreeGrid>





{% endhighlight %}



The output of TreeGrid with CellEditing is as follows.



{ ![](Editing_images/Editing_img1.png) | markdownify }
{:.image }




