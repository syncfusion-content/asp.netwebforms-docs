---
layout: post
title: Server Side Events | TreeView | ASP.NET | Syncfusion
description: server side events for TreeView
platform: aspnet
control: TreeView
documentation: UG
---

# Server Side Events

You can specify the server side events of TreeView in ASP.NET. To set server side event, you can enable any of the following events.

<table>
<tr>
<td>
    {{'**Event**'| markdownify }}
</td>
<td>
    {{'**Event Description**'| markdownify }}
</td>
<td>
    {{'**Event Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
OnNodeChecked
</td>
<td>
Occurs when treeView node checkbox is checked.
</td>
<td>
Event Argument contains parameters are<br/><br/>e.NodeText - Text of TreeView Selected Node<br/><br/>e.NodeID - Id of TreeView Selected Node<br/><br/>e.Checked - Status of TreeView Node Checkbox<br/><br/>e.CurrentCheckedNodes - List of TreeView Current Checked Nodes<br/><br/>e.EventType - Event Name<br/><br/>e.Arguments - Contain keys and values for NodeText,NodeID,Checked and CurrentCheckedNodes<br/><br/></td>
</tr>
<tr>
<td>
OnNodeDropped
</td>
<td>
Occurs when treeView node is dropped.
</td>
<td>
Event Argument contains the following parameters.<br/><br/>e.NodeText - Text of TreeView Selected Node<br/><br/>e.NodeID - Id of TreeView Selected Node<br/><br/>e.TargetNodeDetails –Drop the selected node<br/><br/>e.TargetNodeDetails.id- Id of DragElement <br/><br/>TargetNodeDetails.NodeDetails-Contain keys and values for DragElement <br/><br/>TargetNodeDetails.TargetId-Id of TargetElement<br/><br/>TargetNodeDetails.TargetNodeDetails-Contain keys and values for TargetElement<br/><br/>e.EventType - Event Name<br/><br/>e.Arguments - Contain keys and values for NodeText, NodeID and TargetNodeDetails<br/><br/></td>
</tr>
<tr>
<td>
OnNodeSelected
</td>
<td>
Occurs when treeView node is selected
</td>
<td>
Event Argument contains parameters are<br/><br/>e.NodeText - Text of TreeView Selected Node<br/><br/>e.NodeID - Id of TreeView Selected Node<br/><br/>e.EventType - Event Name<br/><br/>e.Arguments - Contain keys and values for NodeText and NodeID.<br/><br/></td>
</tr>
<tr>
<td>
OnInlineEditValidation
</td>
<td>
Occurs when treeView node is editing.
</td>
<td>
Event Argument contains the following parameters<br/><br/>e.NodeText - Text of TreeView Selected Node<br/><br/>e.NodeID - Id of TreeView Selected Node<br/><br/>e.RenamedNode - Edit the selected node <br/><br/>RenamedNode.id-Id of edited node <br/><br/>RenamedNode.old-Text value of before edited node <br/><br/>RenamedNode.new-Text value of after edited node<br/><br/>e.EventType - Event Name<br/><br/>e.Arguments - Contain keys and values for NodeText, NodeID and RenamedNode<br/><br/></td>
</tr>
</table>

In the ASPX page, add the following button elements to configure TreeView events
    
    {% highlight html %}
    
        <%--Add server side event for TreeView control as follows--%>
    
        <ej:TreeView
            ID="treeview"
            runat="server"
            Height="300px"
            Width="400px"
            ShowCheckbox="true"
            OnNodeChecked="treeview_NodeChecked"
            OnNodeSelected="treeView_NodeSelected"
            OnNodeDropped="treeView_NodeDropped"
            OnInlineEditValidation="treeView_InlineEditValidation"
            AllowDragAndDrop="true"
            AllowDropChild="true"
            AllowDropSibling="true"
            AllowEditing="true">
            <Nodes>
                <ej:TreeViewNode Expanded="True" Text="Artwork">
                    <Nodes>
                        <ej:TreeViewNode Text="Abstract">
                            <Nodes>
                                <ej:TreeViewNode Text="2 Acrylic Mediums"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Creative Acrylic"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Modern Painting"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Canvas Art"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Black white"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Children">
                            <Nodes>
                                <ej:TreeViewNode Text="Preschool Crafts"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="School-age Crafts"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Fabulous Toddler"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Comic / Cartoon">
                            <Nodes>
                                <ej:TreeViewNode Text="Batman"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Adventures of Superman"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Super boy"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Expanded="True" Text="Books">
                    <Nodes>
                        <ej:TreeViewNode Text="Comics">
                            <Nodes>
                                <ej:TreeViewNode Text="The Flash"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Human Target"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Birds of Prey"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Canvas Art"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Black white"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Entertaining"></ej:TreeViewNode>
                        <ej:TreeViewNode Text="Design"></ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Text="Music">
                    <Nodes>
                        <ej:TreeViewNode Text="Classical">
                            <Nodes>
                                <ej:TreeViewNode Text="Avant-Garde"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Medieval"></ej:TreeViewNode>
                                <ej:TreeViewNode Text="Orchestral"></ej:TreeViewNode>
                            </Nodes>
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Mass"></ej:TreeViewNode>
                        <ej:TreeViewNode Text="Folk"></ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
            </Nodes>
        </ej:TreeView>
        
    {% endhighlight %}
    
In the code behind page, configure the server side events of TreeView
    
    {% highlight c# %}
    
    protected void treeView_NodeChecked(object sender, Syncfusion.JavaScript.Web.TreeViewEventArgs e)
    
    {
    
        //e.NodeText – Text value of selected node
    
        //e.NodeID – Id of selected node
    
        //e.Checked – Status of treeview node checkbox 
    
        //e.CurrentCheckedNodes – List of treeview current checked nodes
    
        //e.EventType – Event Name
    
        //e.Arguments – Contain keys and values for NodeText,NodeID,Checked and CurrentCheckedNodes
    
    }
    
    protected void treeView_NodeSelected(object sender, Syncfusion.JavaScript.Web.TreeViewEventArgs e)
    {
    
        //e.NodeText – Text value of selected node
    
        //e.NodeID – Id of selected node
    
        //e.EventType – Event Name
    
        //e.Arguments – Contain keys and values for NodeText and NodeID
    
    }
    
    protected void treeView_NodeDropped(object sender, Syncfusion.JavaScript.Web.TreeViewEventArgs e)
    {
    
        //e.NodeText – Text value of selected node
    
        //e.NodeID – Id of selected node
    
        //e.TargetNodeDetails – Drop the selected node
    
        //e.EventType – Event Name
    
        //e.Arguments – Contain keys and values for NodeText,NodeID and TargetNodeDetails
    
    }
    
    protected void treeView_InlineEditValidation(object sender, Syncfusion.JavaScript.Web.TreeViewEventArgs e) 
    {
    
        //e.NodeText – Text value of selected node
    
        //e.NodeID – Id of selected node
    
        //e.RenamedNode – Edit the selected node
    
        //e.EventType – Event Name
    
        //e.Arguments – Contain keys and values for NodeText,NodeID and RenamedNode
    
    }
    
    {% endhighlight %}
    
    
    