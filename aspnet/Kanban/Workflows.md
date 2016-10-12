---
layout: post
title: WorkFlows | Kanban | ASP.NET Webforms | Syncfusion
description: WorkFlows
platform: aspnet
control: Kanban
documentation: ug
---

# Workflows 


Workflows can be defined to set the flow of card moving between the Kanban column statuses and it is applicable to drag and drop and context menu features.

You can set [`workflows`](https://help.syncfusion.com/js/api/ejkanban#members:workflows) as array of Objects which consists of `key` and `allowedtransitions` properties. The `allowedTransitions` accepts more than one transition of the specific column key mentioned in `key` property.

If a card is to be dragged to not allowed transition columns , then not supported warning symbol will be displayed for denoting the error.
        
The following code example describes the above Workflow behaviour.

{% highlight html %}

    <div id='Kanban'></div>

{% endhighlight %}

{% highlight javascript %}

    <ej:Kanban ID="KanbanBoard" runat="server" KeyField="Status">
       <WorkFlow>
            <ej:KanbanWorkFlow Key="Open"  AllowedTransitions="InProgress" />
        </WorkFlow>
        <Columns>
            <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
            <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
            <ej:KanbanColumn HeaderText="Testing" Key="Testing" />
            <ej:KanbanColumn HeaderText="Done" Key="Close" />
        </Columns>
        <Fields Content="Summary"/>
    </ej:Kanban>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](WorkFlows_images/workflows1.png)

