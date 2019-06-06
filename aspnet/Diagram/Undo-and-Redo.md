---
layout: post
title: Undo-Redo | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to revert/restore the changes using Undo and Redo commands in the Diagram control.
platform: aspnet
control: Diagram
documentation: ug
---

# History Manager

Diagram tracks the history of actions that are performed after loading the time and provides support to reverse and restore those changes.

## Undo and Redo

Diagram provides Built-in support to track the changes that are made through interaction and through public APIs. The changes can be reverted or restored either through short cut keys or through commands.

### Undo redo through short cut keys

Undo redo commands can be executed through short cut keys. Short cut key for undo is ctrl+z and short cut key for redo is ctrl+y.

For more information, refer to [Keyboard Interactions](/aspnet/Diagram/Interaction#keyboard "Keyboard Interactions").

### Undo redo through public APIs

The client side methods `undo` and `redo` help you to revert/restore the changes. The following code example illustrates how to undo/redo the changes through script.

{% highlight js %}

var diagram = $("#Diagram").ejDiagram("instance");

// Reverts the last action performed
diagram.undo();

// Restores the last undone action
diagram.redo();

{% endhighlight %}

## Track custom changes

Diagram provides options to track the changes that are made to custom properties. For example, in case of an employee relationship Diagram, you may need to track the changes in the employee information. The `HistoryManager` of the Diagram model enables you to track such changes.
The following example illustrates how to track such custom property changes.

* Before changing the employee information, save the existing information to history manager by using the client side method `push` of `historyManager`.

The following code example illustrates how to save the existing property values. 

{% highlight js %}

var diagram = $("#diagram").ejDiagram("instance");

//Creates a custom entry and adds that to history manager
var entry = { object: node, prevState: node.empInfo };
diagram.model.historyManager.push(entry);

//Updates the new information
var newValue = { role: "New role" };
node.empInfo = newValue;

{% endhighlight %}

* Change the employee information

{% highlight js %}

//Updates the new information
var newValue = { role: "New role" };
node.empInfo = newValue;

{% endhighlight %}

* Define the methods to handle the custom changes. These methods are called when you try to revert/restore the custom changes.

You need to define the methods to handle the custom changes and you need to assign that to `Undo` and `Redo` properties of `HistoryManager`.
The following code example illustrates how to define methods to handle the custom changes.

{% tabs %}
{% highlight aspx-cs %}

        <ej:Diagram ID="DiagramContent" runat="server" Height="400px" Width="100%" OnClientNodeCollectionChange="nodeCollectionChange">
            <%--  revert and restore the reverted custom action--%>
            <HistoryManager Undo="customUndoRedo" Redo="customUndoRedo">
            <HistoryManager />
        </ej:Diagram>
            
{% endhighlight %}

{% highlight js %}
//Method to handle the custom action
function customUndoRedo(args) {
	var diagram = $("#diagram").ejDiagram("instance");
	var node = args.object;
	var currentState = node.empInfo;

	//Resets the state
	node.empInfo = args.prevState;

	//Saves the previous state
	args.prevState = currentState;
}

{% endhighlight %}
{% endtabs %}
## Group multiple changes 

History manager allows to revert or restore multiple changes through a single undo/redo command. For example, you may need to revert/restore the fill color change of multiple elements at a time.

The client side method `startGroupAction` is used to notify the Diagram to start grouping the changes. The client side method `closeGroupAction` is used to notify to stop grouping the changes. The following code illustrates how to undo/redo fillColor change of multiple elements at a time.

{% highlight js %}

var group = diagram.model.selectedItems

// Start to group the changes
diagram.model.historyManager.startGroupAction();

//Makes the changes
for (var i = 0; i < group.children.length; i++) {
	var option = {};
	var item = group.children[i];
	// Updates the fillColor for all the child elements.
	option.fillColor = args.style.backgroundColor;
	diagram.updateNode(item.name, option);
}

//Ends grouping the changes
diagram.model.historyManager.closeGroupAction();

{% endhighlight %}
