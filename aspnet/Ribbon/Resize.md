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

## Tablet Layout 

Set `IsResponsive` as true to enable resizing in Ribbon.If client width is above  420px or control content exceeds the page then, the ribbon will render in Tablet mode.

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

![Resize_images1](Resize_images/Resize_img1.png)

## Mobile Layout

If client width is less than 420px, the ribbon will render in mobile mode. In which, you can see that ribbon user interface is customized and redesigned for best view in small screens.
The customized features includes responsive tab & group rendering, backstage, gallery and button controls.
   
### Responsive Tab and group

Set `IsResponsive` as true to enable responsive mode in Ribbon.
   

{% highlight html %}

    <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%"  IsResponsive="true">
                        <RibbonTabs>
                            <ej:RibbonTab Id="home" Text="HOME">
                                <TabGroupCollection>
                                   <ej:TabGroup Text="Font" AlignType="Rows">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentGroupCollection>
                                                   <ej:ContentGroup Id="bold" Text="Bold" IsMobileOnly="true" Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Bold" ActivePrefixIcon="e-icon e-ribbon e-resbold" DefaultPrefixIcon ="e-icon e-ribbon e-resbold" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="italic" Text="Italic"  IsMobileOnly="true" Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Italic" ActivePrefixIcon="e-icon e-ribbon e-resitalic" DefaultPrefixIcon="e-icon e-ribbon e-resitalic" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="underline" Text="Underline" IsMobileOnly="true"  Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Underline" ActivePrefixIcon="e-icon e-ribbon e-resunderline" DefaultPrefixIcon="e-icon e-ribbon e-icon e-resunderline"  />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="strikethrough" Text="strikethrough"  Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Strikethrough" ActivePrefixIcon="e-icon e-ribbon strikethrough" DefaultPrefixIcon="e-icon e-ribbon e-icon strikethrough"  />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="superscript" Text="superscript" >
                                                        <ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-icon e-ribbon  e-superscripticon" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                                <ContentDefaults Type="Button" IsBig="false" />
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                        </RibbonTabs>
                    </ej:Ribbon>

{% endhighlight %}

![Resize_images2](Resize_images/responsive1.png)
{:caption}
Ribbon Responsive with tab content 


N> To make the Ribbon control to react as responsive in mobile devices, it is necessary to refer the additional `ej.responsive.css` file in the application.

## Mobile Toolbar Customization

 Set `IsMobileOnly` as true to group control to show the controls 
 in the Mobile Toolbar of the ribbon. For each tab , first row of mobile ribbon will pick and display the controls which is set as `IsMobileOnly` with look adapt to mobile mode.If `IsMobileOnly` property is not defined to any of the control within tab, then by default fist group content will be displayed in first row toolbar.

 To adapt to proper display of controls , following layout will be customized with constants display.

  * First ribbon toolbar and Button controls with min-height. 
  * Drop down control will adapt to full screen width.
  * All button controls icon will be displayed commonly as Top position.
  
  
  {% highlight html %}

       <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%"  IsResponsive="true">
                        <RibbonTabs>
                            <ej:RibbonTab Id="home" Text="HOME">
                                <TabGroupCollection>
                                   <ej:TabGroup Text="Font" AlignType="Rows">
                                        <ContentCollection>
                                            <ej:TabContent>
                                                <ContentGroupCollection>
                                                   <ej:ContentGroup Id="bold" Text="Bold" IsMobileOnly="true" Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Bold" ActivePrefixIcon="e-icon e-ribbon e-resbold" DefaultPrefixIcon ="e-icon e-ribbon e-resbold" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="italic" Text="Italic"  IsMobileOnly="true" Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Italic" ActivePrefixIcon="e-icon e-ribbon e-resitalic" DefaultPrefixIcon="e-icon e-ribbon e-resitalic" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="underline" Text="Underline" IsMobileOnly="true"  Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Underline" ActivePrefixIcon="e-icon e-ribbon e-resunderline" DefaultPrefixIcon="e-icon e-ribbon e-icon e-resunderline"  />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="strikethrough" Text="strikethrough"  Type="ToggleButton">
                                                        <toggleButtonSettings ContentType="ImageOnly" ActiveText="Strikethrough" ActivePrefixIcon="e-icon e-ribbon strikethrough" DefaultPrefixIcon="e-icon e-ribbon e-icon strikethrough"  />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="superscript" Text="superscript" >
                                                        <ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-icon e-ribbon  e-superscripticon" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                                <ContentDefaults Type="Button" IsBig="false" />
                                            </ej:TabContent>
                                        </ContentCollection>
                                    </ej:TabGroup>
                                </TabGroupCollection>
                            </ej:RibbonTab>
                        </RibbonTabs>
                    </ej:Ribbon>

{% endhighlight %}

![Resize_images3](Resize_images/responsive2.png)
{:caption}
Ribbon Responsive with MobileToolbar 

### Customized Features

The customized layout for  Quick Access Toolbar, backstage, gallery can be seen following screen shots.
 
 ![Resize_images3](Resize_images/responsive3.png)
 {:caption}
Ribbon Responsive with Quick Access Toolbar 
 
 ![Resize_images4](Resize_images/responsive4.png)
 ![Resize_images5](Resize_images/responsive5.png)
 {:caption}
Ribbon Responsive with backstage
 
 ![Resize_images6](Resize_images/responsive6.png)
 {:caption}
Ribbon Responsive with gallery



## Group Button Customization 

Based on window size, detailed group is shrined into single button and you can expand group items with group button click.

For each group shirked for resizing, Custom Class will be added based on group text `e-action` whereas `action` is group text. Using this custom class, group button can be customized such as to set icons etc.


{% tabs %}

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
                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-ribbonpaste" />
                                    </ej:ContentGroup>
                                </ContentGroupCollection>
                            </ej:TabContent>
                            <ej:TabContent>
                                <ContentDefaults Width="60" Height="40" IsBig="false" />
                                <ContentGroupCollection>
                                    <ej:ContentGroup Id="cut" ToolTip="Cut" Text="Cut">
                                        <ButtonSettings ContentType="TextAndImage" Type="Button" PrefixIcon="e-icon e-ribbon e-ribboncut" />
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="copy" ToolTip="Copy" Text="Copy">
                                        <ButtonSettings ContentType="TextAndImage" Type="Button" PrefixIcon="e-icon e-ribbon e-ribboncopy" />
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
                                    <ej:ContentGroup Id="fontFamily" ToolTip="Font" Type="DropDownList">
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
                                        <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-new" />
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
                                        <ButtonSettings ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-undo" Click="executeAction" Type="Button" />
                                    </ej:ContentGroup>
                                    <ej:ContentGroup Id="redo" Text="Redo" ToolTip="Redo">
                                        <ButtonSettings ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-redo" Click="executeAction" Type="Button" />
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
                                        <ButtonSettings Type="Button" ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-printlayout" />
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

{% highlight c# %}

     protected void Page_Load(object sender, EventArgs e)
        {
            var fontList = new List<string> { "Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica" };
            var fontsize = new List<string>() { "1pt", "2pt", "3pt", "4pt", "5pt" };
            this.fontFamily.DropdownSettings.DataSource = fontList;
            this.fontsize.DropdownSettings.DataSource = fontsize;
        }


{% endhighlight %}

{% endtabs %}

![Resize_images2](Resize_images/Resize_img2.png)
