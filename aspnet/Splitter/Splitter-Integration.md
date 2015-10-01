---
layout: post
title: Splitter Integration | Splitter | ASP.NET | Syncfusion
description: splitter integration
platform: aspnet
control: Splitter
documentation: ug
---

# Splitter Integration

The Splitter allows you to use other Essential JavaScript products inside the pane. The integrated function of those controls can be used in other panes of the Splitter.

## Configuring other controls in Splitter

The following steps explain the implementation of Splitter integration.

In an ASPX page, define the Splitter control with two panes. The first pane has the TreeView content and the next one contains content that is related to TreeView.

{% highlight html %}

<ej:Splitter Height="280" Width="501" ID="outersplitter" runat="server">

        <ej:SplitPane>

            <div>

                <div class="cont">

                    <h3 class="h3">ASP.NET MVC</h3>

                    <ej:TreeView ID="treeView" runat="server" ClientSideOnNodeSelected="treeClicked">

                        <Nodes>

                            <ej:TreeViewNode Text="Tools">

                                <Nodes>

                                    <ej:TreeViewNode Id="tools" Text="Description"></ej:TreeViewNode>

                                </Nodes>

                            </ej:TreeViewNode>

                            <ej:TreeViewNode Text="Chart">

                                <Nodes>

                                    <ej:TreeViewNode Id="chart" Text="Description"></ej:TreeViewNode>

                                </Nodes>

                            </ej:TreeViewNode>

                            <ej:TreeViewNode Text="Grid">

                                <Nodes>

                                    <ej:TreeViewNode Id="grid" Text="Description"></ej:TreeViewNode>

                                </Nodes>

                            </ej:TreeViewNode>

                        </Nodes>

                    </ej:TreeView>

                </div>

            </div>

        </ej:SplitPane>



        <ej:SplitPane>

            <div>

                <div class="cont">

                    <div class="_content">

                        Select any product from the tree to show the description.

                    </div>

                    <div class="tools des">

                        <h3>Tools</h3>

                        Essential Tools is an collection of user interface components used to create interactive

                    ASP.NET MVC applications.

                    </div>

                    <div class="chart des">

                        <h3>Chart</h3>

                        Essential Chart is a business-oriented charting component.

                    </div>

                    <div class="grid des">

                        <h3>Grid</h3>

                        Essential MVC Grid offers full featured a Grid control with extensive support for

                    Grouping and the display of hierarchical data.

                    </div>

                </div>

            </div>

        </ej:SplitPane>


    </ej:Splitter>

{% endhighlight %}

{% highlight js %}

       function treeClicked(sender, args) {

            if (sender.value == "Description") {

                var content = $('.' + sender.currentElement[0].id).html();

                $('._content').html(content);

            }

        }

{% endhighlight %}



The following screenshot displays the output of the above code example.

 ![](Splitter-Integration_images/Splitter-Integration_img1.png)



