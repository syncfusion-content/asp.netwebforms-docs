---
layout: post
title: Toolbar
description: toolbar
platform: aspnet
control: Gantt
documentation: ug
---

# Toolbar

Gantt control contains toolbar options for editing, searching, expanding and collapsing all records, indent, out dent, delete and add task. You can enable toolbar using the following code example.







{% highlight html %}

<ej:Gantt ID="GanttContainer" runat="server" >//..

        <ToolbarSettings ShowToolbar="true"

         ToolbarItems="add,edit,delete,update,cancel,indent,outdent,collapseAll,expandAll,search" />

 </ej:Gantt>



{% endhighlight %}



The following screenshot shows the toolbar option in Gantt control.



![](Toolbar_images/Toolbar_img1.png)
{:.image }


