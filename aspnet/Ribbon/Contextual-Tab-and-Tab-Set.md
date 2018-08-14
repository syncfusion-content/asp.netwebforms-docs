---
layout: post
title: Contextual Tab and Tab Set | Ribbon | ASP.NET Webforms | Syncfusion
description: contextual tab and tab set
platform: aspnet
control: Ribbon
documentation: ug
---

# Contextual Tabs

Contextual Tabs are collection of Tabs that extended styling and can be shown based on some criteria. Contextual Tabs can be added like `RibbonTabs` including TabGroup and TabContent section. You can set `BackGroundColor` and `BorderColor` to highlight them as Tab set. Contextual tabs can be added or set dynamically in ribbon control using [`addContextualTabs`](https://help.syncfusion.com/api/js/ejribbon#methods:addcontextualtabs) with it's object and index position.

{% highlight html %}

	<ej:Ribbon ID="Ribbon" runat="server" Width="800px">
	
		<ApplicationTab MenuItemID="menu" Type="Menu">
	
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
	
				<RibbonTabCollection>
	
					<ej:RibbonTab Id="Design" Text="DESIGN">
	
						<TabGroupCollection>
	
							<ej:TabGroup ContentID="design" Text="Table Style Options" Type="custom">
	
							</ej:TabGroup>
	
						</TabGroupCollection>
	
					</ej:RibbonTab>
	
				</RibbonTabCollection>
	
			</ej:ContextualTab>
	
			<ej:ContextualTab BackgroundColor="blue" BorderColor="lightblue">
	
				<RibbonTabCollection>
	
					<ej:RibbonTab Id="Tabset1" Text="TABSET1">
	
						<TabGroupCollection>
	
							<ej:TabGroup ContentID="headings" Text="Tabset1 Styles" Type="custom">
	
							</ej:TabGroup>
	
						</TabGroupCollection>
	
					</ej:RibbonTab>
	
					<ej:RibbonTab Id="Tabset2" Text="TABSET2">
						
						<TabGroupCollection>
						
							<ej:TabGroup>
								
								<ContentCollection>
									
									<ej:TabContent>
										
										<ContentGroupCollection>
											
											<ej:ContentGroup Id="uppercase1" Text="uppercase">
												<ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-icon e-ribbon e-uppercase" />
											
											</ej:ContentGroup>
											
											<ej:ContentGroup Id="lowercase1" Text="Lower Case">
												<ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-icon e-ribbon e-lowercase" />
											
											</ej:ContentGroup>
										
										</ContentGroupCollection>
									
									</ej:TabContent>
								
								</ContentCollection>
							
							</ej:TabGroup>
	
						</TabGroupCollection>
	
					</ej:RibbonTab>
	
				</RibbonTabCollection>
	
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
	
	<div id="Contents">Custom Control</div>
	<div id="headings" class="e-headings">
		<div>
			<p>heading</p>
			<p>No Spacing</p>
		</div>
		<div>
			<p class="e-strong">strong content</p>
			<p>Strong</p>
		</div>
		<div>
			<p class="e-emphasis">emphasis content</p>
			<p>Emphasis</p>
		</div>
	</div>
	<table id="design" class="e-designtablestyle">
		<tr>
			<td>
				<input type="checkbox" id="Check2" />
				<label for="Check2">First Column</label>
			</td>
			<td>
				<input type="checkbox" id="check4" checked="checked" />
				<label for="check4">Total Row</label>
			</td>
		</tr>
	</table>

{% endhighlight %}


![](Contextual-Tab-and-Tab-Set_images/Contextual-Tab-and-Tab-Set_img1.png)
