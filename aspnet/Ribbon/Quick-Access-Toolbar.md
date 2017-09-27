---
layout: post
title: Quick Access Toolbar | Ribbon | ASP.NET Webforms | Syncfusion
description: quick access toolbar 
platform: aspnet
control: Ribbon
documentation: ug
---

# Quick Access Toolbar

Quick Access Toolbar provides the shortcuts to the most commonly used commands by placing the controls at the Quick Access Toolbar section. It can be placed at the top or bottom of the Ribbon.

Set `ShowQAT` as true to enable Quick Access Toolbar in Ribbon. It supports the Button, Split Button, Toggle Button controls. The `QuickAccessMode` is used to change the controls state in Quick Access Toolbar. through options as `ToolBar`,`Menu` and `None`. Default value is `None` and QAT toolbar is created with specified controls added in Toolbar.

The `ToolBar` option used to set controls visibility in Quick Access Toolbar.The `Menu` option shows the controls in Quick Access Menu and does not show controls in Quick Access Toolbar.

Once the controls are visible in Toolbar , then controls state will be set as ticked in Quick Access Menu and vice versa.  

The client side event for Quick Access Toolbar menu click is `QatMenuItemClick` and it will be triggered with QAT menu item click.

`More Commands` command provides with Quick Access Menu. This can be customized using `QatMenuItemClick` event, such as to show popup dialog. 


{% highlight html %}

	<ej:Ribbon ID="defaultRibbon" runat="server" Width="500" ShowQAT="true">
		<ApplicationTab MenuItemID="ribbonmenu" Type="Menu">
			<MenuSettings OpenOnClick="false"></MenuSettings>
		</ApplicationTab>
		<RibbonTabs>
			<ej:RibbonTab Id="home" Text="HOME">
				<TabGroupCollection>
					<ej:TabGroup Text="SplitButton" AlignType="Columns">
						<ContentCollection>
							<ej:TabContent>
								<ContentDefaults Width="50" Height="70" />
								<ContentGroupCollection>
									<ej:ContentGroup Id="paste" ToolTip="Paste" Text="paste" Type="SplitButton" QuickAccessMode="ToolBar">
										<SplitButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-ribbonpaste" ButtonMode="Dropdown" TargetID="split" ArrowPosition="Bottom" />
									</ej:ContentGroup>
								</ContentGroupCollection>
							</ej:TabContent>
	
						</ContentCollection>
					</ej:TabGroup>
					<ej:TabGroup Text="Button" AlignType="Rows">
						<ContentCollection>
							<ej:TabContent>
								<ContentGroupCollection>
									<ej:ContentGroup Id="italic" ToolTip="italic" Text="italic" Type="Button" QuickAccessMode="ToolBar">
										<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-icon e-ribbon e-ribbonitalic" />
									</ej:ContentGroup>
								</ContentGroupCollection>
							</ej:TabContent>
						</ContentCollection>
					</ej:TabGroup>
					<ej:TabGroup Text="Toggle" AlignType="Columns">
						<ContentCollection>
							<ej:TabContent>
								<ContentGroupCollection>
									<ej:ContentGroup ToolTip="Bold" Text="bold" Type="ToggleButton" QuickAccessMode="ToolBar">
										<ToggleButtonSettings defaultText="Bold" activeText="Bold" defaultPrefixIcon="e-icon e-ribbon bold" activePrefixIcon="e-icon e-ribbon bold" />
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
	<ul id="split">
		<li><span>Paste</span></li>
	</ul>
	<style type="text/cs">
				.e-ribbon .e-rbnquickaccessbar .e-ribbonpaste:before {
				font-size: 27px;
				left: -5px;
				top: -6px;
			}
			.e-ribbon .e-ribbonpaste:before {
				font-family: 'ej-ribbonfont';
				content: "\e169";
				font-size: 36px;
				position: relative;
				left: -9px;
				top: -4px;
			}
			.e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
				font-family: 'ej-ribbonfont';
				font-size: 16px;
				left: -1px;
				position: relative;
				top: -1px;
			}
			.e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
				content: "\e163";
			}
		
			.e-ribbon .e-rbnquickaccessbar .e-undo::before {
				font-size: 18px;
				line-height: 12px;
				text-indent: -3px;
			}    
	
		</style>

{% endhighlight %}

![](Quick-Access-Toolbar_images/Quick-Access-toolbar_img1.png)