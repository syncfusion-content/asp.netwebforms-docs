---
layout: post
title: AddContextualTabs | Ribbon | ASP.NET Webforms | Syncfusion
description: addcontextualtabs
platform: aspnet
control: Ribbon
documentation: ug
---

# AddContextualTabs

This method is used to add contextual tabs dynamically.This method has two arguments addContextualTabs(Contextualtabs,index)

* Contextualtabs: Collection of the contextual tabs that contextual tab needs to add.
* Index: Index in which the tab is to be added.It is optional argument. When this argument is not given, by default the tab is added at the last position.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800">

            <ApplicationTab MenuItemID="menu" Type="Menu">

            </ApplicationTab>

            <RibbonTabs>

                <ej:RibbonTab Id="RibbonTab1" Text="INSERT">

                    <TabGroupCollection>

                        <ej:TabGroup Text="Clipboard">

                            <ContentCollection>

                                <ej:TabContent>

                                    <ContentGroupCollection>

                              <ej:ContentGroup Id="ContentGroup1" Type="Custom" ContentID="paste">

                                        </ej:ContentGroup>

                                    </ContentGroupCollection>

                                </ej:TabContent>

                            </ContentCollection>

                        </ej:TabGroup>

                    </TabGroupCollection>

                </ej:RibbonTab>



            </RibbonTabs>

        </ej:Ribbon>

<ul id="menu">

<li><a>FILE</a></li>

</ul>

<div id="paste" style="height:40px;width:43px;">Paste</div>

    <div id="design">ContextualTab</div>

<script type="text/javascript">

var ribbonObj;

   var contextualTab = {

            backgroundColor: "#FCFBEB", borderColor: "#F2CC1C",

            tabs: [

            {

                id: "Design", text: "DESIGN", groups: [{

                    text: "Table Style", type: "custom", contentID: "design"

                }

                ]

            }]

        }

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.addContextualTabs(contextualTab, 2);



});

</script>



{% endhighlight %}



The following screenshot displays the output of the above code example.

![C:/Users/Giftline/Desktop/a.png](AddContextualTabs_images/AddContextualTabs_img1.png)










