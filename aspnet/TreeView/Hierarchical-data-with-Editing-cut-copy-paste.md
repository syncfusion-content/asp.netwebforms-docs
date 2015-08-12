---
layout: post
title: Hierarchical-data-with-Editing-cut-copy-paste
description: hierarchical data with editing-cut-copy-paste
platform: aspnet
control: TreeView
documentation: ug
---

## Hierarchical data with Editing-cut-copy-paste

The TreeView control permits you to edit a node and also allows you to cut, copy and paste the node in TreeView. You can edit the tree node name when it is required. This is achieved by using the AllowEditing property. By setting the property as “True”, you can select a node and press F2 or double click the node to initiate editing.

The following steps explain how to enable the AllowEditing property for TreeView.

In the ASPX page, add an elements to configure TreeView.       

{% highlight html %}

<ej:TreeView ID="treeview1" runat="server" AllowEditing="true">

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



 ![](Hierarchical-data-with-Editing-cut-copy-paste_images/Hierarchical-data-with-Editing-cut-copy-paste_img1.png) 




