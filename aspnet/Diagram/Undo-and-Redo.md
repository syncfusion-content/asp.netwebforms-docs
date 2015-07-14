---
layout: post
title: Undo-and-Redo
description: undo and redo
platform: aspnet
control: Diagram
documentation: ug
---

## Undo and Redo

The Undocommand reverses the last edited action performed on the Diagram. For example, some of the basic operations performed on Diagram objects such as translation, rotation, resizing, grouping, ungrouping, changing z-order, addition, deletion and so on, can be reversed. The Redo command restores the last editing action when no other action has occurred since the last undo. Diagram provides public API undo()/redo() to run the undo/redo commands and the following code illustrate this.

{% highlight js %}

[JS]

//undo

var diagram = $("#Diagram").ejDiagram("instance");

diagram.undo();



//redo

diagram.redo();



{% endhighlight %}



