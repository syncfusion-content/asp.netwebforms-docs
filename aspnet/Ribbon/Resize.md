---
layout: post
title: Resize | Ribbon | ASP.NET Webforms | Syncfusion
description: resize 
platform: aspnet
control: Ribbon
documentation: ug
---

# Resize 

Ribbon control supports resizing functionality .To enable resizing in the ribbon, you need to set the AllowResizing property to true. When you resize the ribbon window, the Ribbon control automatically resizes to fit into the layout panel. 



{% highlight html %}




     <ej:Ribbon ID="defaultRibbon" runat="server" Width="70%" AllowResizing="true">

                        <ApplicationTab MenuItemID="ribbonmenu" Type="Menu">

                        </ApplicationTab>

                        <RibbonTabs>

                            <ej:RibbonTab Id="home" Text="HOME">

                                <TabGroupCollection>

                                    <ej:TabGroup Text="Clipboard" AlignType="Rows">

                                        <ContentCollection>

                                            <ej:TabContent>

                                              <ContentGroupCollection>

                                              <ej:ContentGroup Id="cut" Text="Cut"/>

                                              <ej:ContentGroup Id="copy" Text="Copy"/>   

                                                </ContentGroupCollection>

                                            </ej:TabContent>

                                        </ContentCollection>

                                    </ej:TabGroup>

                                    <ej:TabGroup Text="Font" AlignType="Rows">

                                     <ContentCollection>

                                      <ej:TabContent>

                                        <ContentGroupCollection>

                                         <ej:ContentGroup Id="bold" Text="Bold"/>

                                         <ej:ContentGroup Id="italic" Text="Italic" />

                                         <ej:ContentGroup Id="underline" Text="Underline" />

                                         <ej:ContentGroup Id="strikethrough" Text="Strikethrough" />

                                         </ContentGroupCollection>

                                          <ContentDefaults Height="70" />

                                        </ej:TabContent>

                                        </ContentCollection>

                                    </ej:TabGroup>

                                    <ej:TabGroup Text="New" AlignType="Columns">

                                        <ContentCollection>

                                            <ej:TabContent>

                                              <ContentGroupCollection>

                                               <ej:ContentGroup Id="new" Text="New"/>

                                                </ContentGroupCollection>

                                            </ej:TabContent>

                                        </ContentCollection>

                                    </ej:TabGroup>

                                    <ej:TabGroup Text="Actions" AlignType="Rows">

                                        <ContentCollection>

                                            <ej:TabContent>

                                             <ContentGroupCollection>

                                              <ej:ContentGroup Id="undo" Text="Undo"/>

                                              <ej:ContentGroup Id="redo" Text="Redo"/>

                                               </ContentGroupCollection>

                                            </ej:TabContent>

                                        </ContentCollection>

                                    </ej:TabGroup>

                                </TabGroupCollection>

                            </ej:RibbonTab>

                        </RibbonTabs>

                    </ej:Ribbon>

                </div>

                <ul id="ribbonmenu">

                    <li><a>FILE</a>

                <ul><li><a>New</a></li></ul>

                    </li>

                </ul>





{% endhighlight %}





The following screenshot displays Ribbon control without resizing the window.



![C:/Users/Giftline/Desktop/a.png](Resize_images/Resize_img1.png)














When you resize the window, the ribbon groups are converted  into group button based on the window width.When you click the group button, the corresponding group items are displayed .The following screenshot displays the Ribbon control when  clicking the group button Actions

![](Resize_images/Resize_img2.png)


