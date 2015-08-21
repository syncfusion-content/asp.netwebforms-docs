---
layout: post
title: Accessibility
description: accessibility
platform: aspnet
control: TreeView
documentation: ug
---

## Accessibility

TreeView provides full keyboard support. You can interact with the TreeView control by using the keyboard. It is compatible with the standard keyboard navigation and you can focus on TreeView with a predefined Alt and Key combination. Also, you can navigate through the nodes, expand or collapse, select, check and uncheck nodes with the provided shortcut keys. You can access the TreeView with the shortcut keys by using the AllowKeyboardNavigation property.

This feature is mainly useful for all the keyboard users to access the TreeView with the keyboard shortcut keys.

The following table showcases the various keyboard shortcuts available in the TreeView control. 

_Keyboard Shortcuts_

<table>
<tr>
<th>
Keys </th><th>
Functions</th></tr>
<tr>
<td>
      Alt+j</td><td>
Focuses the control.</td></tr>
<tr>
<td>
F2</td><td>
Edit the selected node. </td></tr>
<tr>
<td>
Ctrl + X</td><td>
Cut the selected node.</td></tr>
<tr>
<td>
Ctrl + C</td><td>
Copy the selected node.</td></tr>
<tr>
<td>
Ctrl + V</td><td>
Paste the cut or copied nodes to selected node.</td></tr>
<tr>
<td>
Delete key</td><td>
Delete the selected node.</td></tr>
<tr>
<td>
Down</td><td>
Selected next node.</td></tr>
<tr>
<td>
Up</td><td>
Selected previous node.</td></tr>
<tr>
<td>
Right</td><td>
Expand selected node. </td></tr>
<tr>
<td>
Left</td><td>
Collapse selected node.</td></tr>
<tr>
<td>
Enter</td><td>
Select node.</td></tr>
<tr>
<td>
Space</td><td>
Toggle Checks and Unchecks.</td></tr>
<tr>
<td>
Home</td><td>
Selected first child node.</td></tr>
<tr>
<td>
End</td><td>
Selected last child node.</td></tr>
</table>


The following steps explain how to enable the AllowKeyboardNavigation property for TreeView.

In the ASPX page, add elements to configure TreeView.

{% highlight html %}

<ej:TreeView ID="treeview1" runat="server" ShowCheckbox="true" AllowEditing="true" AllowKeyboardNavigation="true">

    <Nodes>

        <ej:TreeViewNode Expanded="True" Text="Favorites">

            <Nodes>

                <ej:TreeViewNode Text="Desktop">

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Downloads">

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Recent places">

                </ej:TreeViewNode>

            </Nodes>

        </ej:TreeViewNode>

        <ej:TreeViewNode Expanded="True" Text="Libraries">

            <Nodes>

                <ej:TreeViewNode Text="Documents">

                    <Nodes>

                        <ej:TreeViewNode Text="My Documents">

                        </ej:TreeViewNode>

                        <ej:TreeViewNode Text="Public Documents">

                        </ej:TreeViewNode>

                    </Nodes>

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Pictures">

                    <Nodes>

                        <ej:TreeViewNode Text="My Pictures">

                        </ej:TreeViewNode>

                        <ej:TreeViewNode Text="Public Pictures">

                        </ej:TreeViewNode>

                    </Nodes>

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Music">

                    <Nodes>

                        <ej:TreeViewNode Text="My Music">

                        </ej:TreeViewNode>

                        <ej:TreeViewNode Text="Public Music">

                        </ej:TreeViewNode>

                    </Nodes>

                </ej:TreeViewNode>

            </Nodes>

        </ej:TreeViewNode>

        <ej:TreeViewNode Text="Computer">

            <Nodes>

                <ej:TreeViewNode Text="Folder(C)">

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Folder(D)">

                </ej:TreeViewNode>

                <ej:TreeViewNode Text="Folder(E)">

                </ej:TreeViewNode>

            </Nodes>

        </ej:TreeViewNode>

    </Nodes>

</ej:TreeView>



{% endhighlight %}



### Define JavaScript for customizing the TreeView



{% highlight js %}

<%--Focus the TreeView in the script--%>

<script type="text/javascript">

    <%--Control focus key--%>

    $(document).on("keydown", function (e) {

        if (e.altKey && e.keyCode === 74) {

            <%--j- key code--%>

            $(".e-treeview.e-js").focus();

        }

    });	

</script>



{% endhighlight %}



![](Accessibility_images/Accessibility_img1.png) 





