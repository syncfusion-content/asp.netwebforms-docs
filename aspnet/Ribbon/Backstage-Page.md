---
layout: post
title: Backstage Page | Ribbon | ASP.NET Webforms | Syncfusion
description: backstage page
platform: aspnet
control: Ribbon
documentation: ug
---
# Backstage Page 


Ribbon control has Backstage page support.The left side of the backstage page contains backstage tab and button items,right side of the backstage page contains UserControl items.To render ribbon with backstage page set _**ApplicationTab’s** __**Type**_ as _**"Backstage"**_ and _**Text**_ property in _**ApplicationTab**_ to set text for Apllication tab.

 We can set height and width to backstage page using properties _**Height**_ and _**Width**_.

* _**Id**_ **–** Specify id of backstage tab and button .

* _**Text**_**–** Specify text of backstage tab and button.

* _**ContentID**_ **–**Specify id of UserControl’s Parent item.

* _**ItemType**_ **–**Specify the type of backstage page item to render backstage tab or button.

* _**ItemType.Tab**_ **–**to render backstage tab.

* _**EnableSeparator**_ **–**Set true to enable separator between backstage button and tab items.

{% highlight html %}

   <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%" Create="createControl">
   
            <ApplicationTab Type="Backstage">
            
                <BackstageSettings HeaderWidth="120" Text="FILE" Height="350" Width="1000">
                
                <PageCollection>
                
                    <ej:BackstagePage Id="info" Text="Info" ItemType="Tab" ContentID="infoCon"/>
                    
                    <ej:BackstagePage Id="newtab" Text="New" ContentID="newCon"/>
                    
                    <ej:BackstagePage Id="close" Text="Close" EnableSeparator="true" ItemType="Button"/>
                    
                    <ej:BackstagePage Id="account" Text="Office Account" ContentID="accountCon"/>
                    
                </PageCollection>
                
              </BackstageSettings>
              
            </ApplicationTab>
            
            <RibbonTabs>
            
                <ej:RibbonTab Id="home" Text="HOME">
                
                    <TabGroupCollection>
                    
                        <ej:TabGroup Text="New" AlignType="Columns" EnableGroupExpander="true">
                        
                        </ej:TabGroup> 
                                             
                    </TabGroupCollection>
                    
                </ej:RibbonTab>  
                            
            </RibbonTabs>
            
        </ej:Ribbon>
        
       <div id="infoCon">Info Tab</div>
       <div id="newCon">New Tab</div>
       <div id="accountCon">Account Tab</div>
        
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Backstage-Page_images/Backstage-Page_img1.png)
