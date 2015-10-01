---
layout: post
title: Ul Li Template | TreeView | ASP.NET | Syncfusion
description: ul-li template
platform: aspnet
control: TreeView
documentation: ug
---

# Ul-Li Template

The TreeView supports template technology, allowing you to completely customize the element’s appearance and layout. The nodes are provided with rich template support, so that the customizations are done in an easier manner. The look of the TreeView default elements are completely modified by creating a specific template, defining how an element is going to be rendered. You can customize the TreeView appearance, and give it a new look or style. 

The following steps explain configuring the template option for TreeView.

In the ASPX page, add an element to configure TreeView.

{% highlight html %}

<ej:TreeView ID="treeview3" runat="server">

    <Nodes>

        <ej:TreeViewNode Expanded="True" Text="Favorites">

            <Nodes>

                <ej:TreeViewNode SpriteCssClass="cont-del" Text="Desktop">

                </ej:TreeViewNode>

                <ej:TreeViewNode SpriteCssClass="cont-del" Text="Downloads">

                </ej:TreeViewNode>

                <ej:TreeViewNode SpriteCssClass="cont-del" Text="Recent places">

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



### Define JavaScript for Ui-Li template

In the following script example, you can delete the child node by clicking the Delete icon. This is achieved by the removeNode method in TreeView.

{% highlight js %}

<%--Delete the Child node Icon for TreeView control in script. --%>

<script type="text/javascript">

    $(function () {

        var treeObj = $("#<%=treeview.ClientID%>").data("ejTreeView");

        $("#<%=treeview.ClientID%>").find(".cont-del").bind("click", function (e) {

            treeObj.removeNode($(e.target).parents("li").first());

        });

    });

</script>

{% endhighlight %}


### Define css for Ui-Li template 

{% highlight css %}

<style class="cssStyles">

    .cont-details

    {

        margin-top: 10px;

        margin-left: 10px;

        font-size: 13px;

        font-family: Georgia;

        color: black;

        width: 100px;

        text-align: left;

    }

    .cont-del

    {

        background: url("../images/treeview/remove-icon.png") no-repeat 50% 50%;

        width: 12px;

        height: 12px;

        display: inline-block;

        cursor: pointer;

    }

</style>

{% endhighlight %}

![](Ul-Li-Template_images/Ul-Li-Template_img1.png) 