---
layout: post
title: Resize | Ribbon | ASP.NET Webforms | Syncfusion
description: resize 
platform: aspnet
control: Ribbon
documentation: ug
---

# Resize 

Ribbon control dynamically resizes to display possible number of controls in the optimal layout as the application window size changes.

As the window is narrowed, controls in the Ribbon will be combined as group button with dropdown arrow, in which controls can be expanded with dropdown arrow.

## IsResponsive 

Set `IsResponsive` as true to enable resizing in Ribbon.

{% highlight html %}

        <ej:Ribbon ID="defaultRibbon1" runat="server" Width="20%"  IsResponsive="true">
        <ApplicationTab MenuItemID="ribbonmenu" Type="Menu">
            <MenuSettings OpenOnClick="false"></MenuSettings>
        </ApplicationTab>
        <RibbonTabs>
            <ej:RibbonTab Id="home" Text="HOME">
                <TabGroupCollection>
                    <ej:TabGroup Text="Clipboard">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Height="70" Width="40" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="cut" Text="Cut">
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="copy" Text="Copy">
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                    <ej:TabGroup Text="Font">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Height="70" Width="40" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="bold" Text="Bold">
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="italic" Text="Italic">
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                    <ej:TabGroup Text="Align">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Height="70" Width="40" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="left" Text="Left">
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="right" Text="Right">
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                </TabGroupCollection>
            </ej:RibbonTab>
        </RibbonTabs>
    </ej:Ribbon>
    <ul id="ribbonmenu">
        <li><a>FILE</a>
            <ul>
                <li><a>New</a></li>
                <li><a>Open</a></li>
            </ul>
        </li>
    </ul>

{% endhighlight %}

![](Resize_images/Resize_img1.png)

## Group Button Customization 

Based on window size, detailed group is shrined into single button and you can expand group items with group button click.

For each group shirked for resizing, Custom Class will be added based on group text.ie, `e-action` whereas `action` is group text. Using this custom class, group button can be customized such as to set icons etc.

{% highlight html %}

        <ej:Ribbon ID="defaultRibbon" runat="server" Width="46%" AllowResizing="true" Create="createControl">
        <ApplicationTab MenuItemID="ribbonmenu" Type="Menu">
            <MenuSettings OpenOnClick="false"></MenuSettings>
        </ApplicationTab>
        <RibbonTabs>
            <ej:RibbonTab Id="home" Text="HOME">
                <TabGroupCollection>
                    <ej:TabGroup Text="Clipboard" AlignType="Columns">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Width="50" Height="70" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="paste" ToolTip="Paste">
                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                            <ej:TabContent>
                                <ContentDefaults Width="60" Height="40" IsBig="false" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="cut" ToolTip="Cut" Text="Cut">
                                        <ButtonSettings ContentType="TextAndImage" Type="Button" PrefixIcon="e-ribbon e-ribboncut" />
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="copy" ToolTip="Copy" Text="Copy">
                                        <ButtonSettings ContentType="TextAndImage" Type="Button" PrefixIcon="e-ribbon e-ribboncopy" />
                                    </ej:ContentGroup>
    
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                    <ej:TabGroup Text="Font" AlignType="Rows">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Height="28" Type="DropDownList" IsBig="false" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">
                                        <DropdownSettings Text="Segoe UI" Width="150" Select="executeAction"></DropdownSettings>
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="fontsize" ToolTip="FontSize" Type="DropDownList">
                                        <DropdownSettings Text="1pt" Width="65" Select="executeAction"></DropdownSettings>
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                    <ej:TabGroup Text="New" AlignType="Columns">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="new" Text="New" ToolTip="New" Type="Button">
                                        <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-new" />
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                                <ContentDefaults Width="60" Height="40" Type="Button" />
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                    <ej:TabGroup Text="Actions" AlignType="Rows">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Type="Button" Height="70" Width="40" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="undo" Text="Undo" ToolTip="Undo" IsBig="false">
                                        <ButtonSettings ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-undo" Click="executeAction" Type="Button" />
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="redo" Text="Redo" ToolTip="Redo">
                                        <ButtonSettings ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-redo" Click="executeAction" Type="Button" />
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                </TabGroupCollection>
            </ej:RibbonTab>
            <ej:RibbonTab Id="layout" Text="LAYOUT">
                <TabGroupCollection>
                    <ej:TabGroup Text="Print Layout" AlignType="Rows">
                        <ContentCollection>
                            <ej:TabContent>
                                <ContentDefaults Height="70" Width="80" Type="Button" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="printlayout" Text="Print Layout" ToolTip="Print Layout">
                                        <ButtonSettings Type="Button" ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-printlayout" />
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                        </ContentCollection>
                    </ej:TabGroup>
                </TabGroupCollection>
            </ej:RibbonTab>
        </RibbonTabs>
    </ej:Ribbon>
    
    <ul id="ribbonmenu">
        <li><a>FILE</a>
            <ul>
                <li><a>New</a></li>
                <li><a>Open</a></li>
            </ul>
        </li>
    </ul>
    <style>
            .e-ribbon .e-New:before, .e-ribbon .e-Actions:before {
                font-family: "ej-ribbonfont";
                font-size: 28px;
                line-height: 35px;
            }
            .e-ribbon .e-New:before {
                /*e-New to group “New” */
                content: "\e167";            
                text-indent: -1.5px;
            }
            .e-ribbon .e-Actions:before {
                /*e-Actions to group “Actions”*/
                content: "\e177";
                text-indent: 7px;
            }
    
        </style>

{% endhighlight %}

![](Resize_images/Resize_img2.png)
