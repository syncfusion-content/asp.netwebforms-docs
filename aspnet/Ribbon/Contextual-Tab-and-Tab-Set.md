---
layout: post
title: Contextual-Tab-and-Tab-Set
description: contextual tab and tab set
platform: aspnet
control: Ribbon
documentation: ug
---

## Contextual Tab and Tab Set

You can add _Contextual Tabs_ and _Tab Set_ in the _Ribbon_ control. In _ContextualTabs_ tag, use _RibbonTab_ tag to add _contextual tabs_ and _contextual tab set_. In _ContextualTab_ tag, use _BackgroundColor_ property to apply background color to the _Contextual Tabs and Tab Set_. Use _BorderColor_ property to apply border color to the _Contextual Tabs and Tab Set._



{% highlight html %}

[ASP.NET]



[ASPX]

<ej:Ribbon ID="Ribbon" runat="server" Width="800px">

        <ApplicationTab ItemID="menu" Type="ApplicationMenu">

            <MenuSettings OpenOnClick="false"></MenuSettings>

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="CustomControls" Type="custom" AlignType="Columns" ContentID="Contents">

                    </ej:TabGroup>

                </TabGroupCollection>

            </ej:RibbonTab>

        </RibbonTabs>

        <ContextualTabs>

            <ej:ContextualTab BackgroundColor="#FCFBEB" BorderColor="#F2CC1C">

                <RibbonTabCollection >

                    <ej:RibbonTab Id="Design" Text="DESIGN">

                        <TabGroupCollection>

                            <ej:TabGroup ContentID="contextualTab" Text="Table Style Options" Type="custom">

                            </ej:TabGroup>

                        </TabGroupCollection>

                    </ej:RibbonTab>

                </RibbonTabCollection >

            </ej:ContextualTab>

            <ej:ContextualTab BackgroundColor="blue" BorderColor="lightblue">

                <RibbonTabCollection >

                    <ej:RibbonTab Id="Tabset1" Text="TABSET1">

                        <TabGroupCollection>

                            <ej:TabGroup ContentID="contextualTabset1" Text="Tabset1 Styles" Type="custom">

                            </ej:TabGroup>

                        </TabGroupCollection>

                    </ej:RibbonTab>

                    <ej:RibbonTab Id="Tabset2" Text="TABSET2">

                        <TabGroupCollection>

                            <ej:TabGroup ContentID="contextualTabset2" Text="Tabset2 Styles" Type="custom">

                            </ej:TabGroup>

                        </TabGroupCollection>

                    </ej:RibbonTab>

                </RibbonTabCollection >

            </ej:ContextualTab>



        </ContextualTabs>

    </ej:Ribbon>



   <ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

            </ul>

        </li>

    </ul>

    <div id="Contents">Custom control</div>

    <div id="contextualTab">

        <button id="contextualBtn">Contextual Tab</button>

    </div>

    <div id="contextualTabset1">

        <button id="contextualTabsetBtn1">Contextual Tabset1</button>

    </div>

    <div id="contextualTabset2">

        <button id="contextualTabsetBtn2">Contextual Tabset2</button>

    </div>



{% endhighlight %}



The following screenshot illustrates _Ribbon_ with _Contextual Tabs and Tab Set_.

{ ![](Contextual-Tab-and-Tab-Set_images/Contextual-Tab-and-Tab-Set_img1.png) | markdownify }
{:.image }


