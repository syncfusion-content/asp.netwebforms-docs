---
layout: post
title: RTL Support | TreeView | ASP.NET | Syncfusion
description: rtl support
platform: aspnet
control: TreeView
documentation: ug
---

# RTL Support

TreeView supports right-to-left layout and the node text is displayed in the RTL languages. Arabic and Hebrew are languages written from right to left. When you desire to change the display of TreeView as right to left direction, you can do so by using the EnableRTL property. To enable or disable this option, set the appropriate value for the EnableRTL property. When EnableRTL is enabled, the appearance of the TreeView is displayed in the right to left direction. You can display the TreeView as right to left direction by using this feature.

The following steps explain enabling the EnableRTL property for TreeView.

In the ASPX page, add an element to configure TreeView.

{% highlight html %}

<ej:TreeView ID="treeview1" runat="server" EnableRTL="true">

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



![](RTL-Support_images/RTL-Support_img1.png) 





























