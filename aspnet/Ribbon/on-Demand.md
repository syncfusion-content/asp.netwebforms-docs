---
layout: post
title: OnDemand | Ribbon | ASP.NET Webforms | Syncfusion
description: OnDemand
platform: aspnet
control: Ribbon
documentation: ug
---

# Load on Demand

Set `EnableOnDemand` as true to enable load tab and backstage contents dynamically. Loading content on demand improves the initial rendering time of the ribbon by rendering tab and backstage content when tabs and backstage items are clicked.
 
{% highlight html %}
          
            <div id="newCon">
                    <table>
                        <tr>
                            <td>
                                <button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="accountCon">
                    <div class="e-userDiv">
                        <span>User Information</span>
                        <div>
                            <div class="e-accuser e-newpageicon"></div>
                            <div class="e-userCon">
                                <div>user</div>
                                <div>any@syncfusion.com</div>
                            </div>
                        </div>
                    </div>
                    <a href="#">Sign out</a>
                </div>
                <div>
                    <ej:Ribbon ID="defaultRibbon" runat="server" Width="50%" EnableOnDemand="true">
                       <ApplicationTab Type="Backstage">
                          <BackstageSettings HeaderWidth="125" Text="FILE" Height="360" Width="600">
                            <PageCollection>
                               <ej:BackstagePage Id="new" Text="New" ContentID="newCon"/>
                               <ej:BackstagePage Id="close" Text="Close"  ItemType="Button" EnableSeparator="true"/>
                               <ej:BackstagePage Id="account" Text="Office Account" ContentID="accountCon"/>
                            </PageCollection>
                          </BackstageSettings>
                        </ApplicationTab>
                          <RibbonTabs>
                            <ej:RibbonTab Id="home" Text="HOME">
                                <TabGroupCollection>
                                     <ej:TabGroup Text="Clipboard" AlignType="Columns">
                                       <GroupExpanderSettings ToolTip="Clipboard"></GroupExpanderSettings>
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentDefaults Width="50" Height="75" Type="Button" IsBig="true"/>
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="paste" ToolTip="Paste" Text="paste" Type="Button">
                                                        <ButtonSettings Type="Button" ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-ribbonpaste"/>
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                    <ej:TabGroup Text="New" AlignType="Columns">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="new1" Text="New" ToolTip="New" Type="Button">
                                                        <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-new" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                                <ContentDefaults Width="60" Height="70" Type="Button" />
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                            <ej:RibbonTab Id="layout" Text="LAYOUT">
                                <TabGroupCollection>
                                    <ej:TabGroup Text="Alignment" AlignType="Rows">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentDefaults Type="Button" IsBig="false" />
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="bullet" Text="Bullet Format" ToolTip="Bullets">
                                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-bullet" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="number" Text="Number Format" ToolTip="Numbering">
                                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-numbericon" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                        </RibbonTabs>
                    </ej:Ribbon>
                 <div>
       <script>
           $("#btn1").ejButton({
              size: "large",
              height: 200,
              width: 225,
              contentType: "textandimage",
              imagePosition: "imagetop",
              prefixIcon: "e-icon e-blank e-infopageicon"
           });
     </script>
    
    <style type="text/css">
         .e-accuser {
           background-image: url("../Content/ejthemes/common-images/ribbon/User.jpg");
         }
        .e-blank {
           background-image: url("../Content/ejthemes/common-images/ribbon/blank.png");
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>
    
{% endhighlight %}

![](On_Demand_images/onDemand_img1.png)

# Initially Collapsible

Set `Collapsible` as true to render ribbon control in collapsed state, which results ribbon tabs to render without any content initially.
While using initially collapsible ribbon with `EnableOnDemand` feature improves the performance by reducing initial loading time of ribbon.

{% highlight html %}
          
            <div id="newCon">
                    <table>
                        <tr>
                            <td>
                                <button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="accountCon">
                    <div class="e-userDiv">
                        <span>User Information</span>
                        <div>
                            <div class="e-accuser e-newpageicon"></div>
                            <div class="e-userCon">
                                <div>user</div>
                                <div>any@syncfusion.com</div>
                            </div>
                        </div>
                    </div>
                    <a href="#">Sign out</a>
                </div>
                <div>
                    <ej:Ribbon ID="defaultRibbon" runat="server" Width="50%" EnableOnDemand="true" Collapsible="true">
                       <ApplicationTab Type="Backstage">
                          <BackstageSettings HeaderWidth="125" Text="FILE" Height="360" Width="600">
                            <PageCollection>
                               <ej:BackstagePage Id="new" Text="New" ContentID="newCon"/>
                               <ej:BackstagePage Id="close" Text="Close"  ItemType="Button" EnableSeparator="true"/>
                               <ej:BackstagePage Id="account" Text="Office Account" ContentID="accountCon"/>
                            </PageCollection>
                          </BackstageSettings>
                        </ApplicationTab>
                          <RibbonTabs>
                            <ej:RibbonTab Id="home" Text="HOME">
                                <TabGroupCollection>
                                     <ej:TabGroup Text="Clipboard" AlignType="Columns">
                                       <GroupExpanderSettings ToolTip="Clipboard"></GroupExpanderSettings>
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentDefaults Width="50" Height="75" Type="Button" IsBig="true"/>
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="paste" ToolTip="Paste" Text="paste" Type="Button">
                                                        <ButtonSettings Type="Button" ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-ribbonpaste"/>
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                    <ej:TabGroup Text="New" AlignType="Columns">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="new1" Text="New" ToolTip="New" Type="Button">
                                                        <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-new" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                                <ContentDefaults Width="60" Height="70" Type="Button" />
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                            <ej:RibbonTab Id="layout" Text="LAYOUT">
                                <TabGroupCollection>
                                    <ej:TabGroup Text="Alignment" AlignType="Rows">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentDefaults Type="Button" IsBig="false" />
                                                <ContentGroupCollection>
                                                    <ej:ContentGroup Id="bullet" Text="Bullet Format" ToolTip="Bullets">
                                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-bullet" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="number" Text="Number Format" ToolTip="Numbering">
                                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-numbericon" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                        </RibbonTabs>
                    </ej:Ribbon>
                 <div>
       <script>
           $("#btn1").ejButton({
              size: "large",
              height: 200,
              width: 225,
              contentType: "textandimage",
              imagePosition: "imagetop",
              prefixIcon: "e-icon e-blank e-infopageicon"
           });
     </script>
    
    <style type="text/css">
         .e-accuser {
           background-image: url("../Content/ejthemes/common-images/ribbon/User.jpg");
         }
        .e-blank {
           background-image: url("../Content/ejthemes/common-images/ribbon/blank.png");
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>
    
{% endhighlight %}

![](On_Demand_images/onDemand_img2.png)