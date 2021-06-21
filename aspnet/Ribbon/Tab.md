---
layout: post
title:  Tab | Ribbon | ASP.NET Webforms | Syncfusion
description: tab
platform: aspnet
control: Ribbon
documentation: ug
---

# Tab

RibbonTabs is a collection of control `TabGroup` which enables you to organize related commands into single view.  Tabs can be added to Ribbon using `RibbonTabs` property. `Id` & `Text` properties are used to set unique ID and header text to RibbonTabs.
The manipulation of given text tab in the ribbon control can be done by using  [`addTab`](https://help.syncfusion.com/api/js/ejribbon#methods:addtab), [`removeTab`](https://help.syncfusion.com/api/js/ejribbon#methods:removetab), [`hideTab`](https://help.syncfusion.com/api/js/ejribbon#methods:hidetab),
[`showTab`](https://help.syncfusion.com/api/js/ejribbon#methods:showtab) methods and [`tabAdd`](https://help.syncfusion.com/api/js/ejribbon#events:tabadd), [`tabCreate`](https://help.syncfusion.com/api/js/ejribbon#events:tabcreate), [`tabRemove`](https://help.syncfusion.com/api/js/ejribbon#events:tabremove), [`tabClick`](https://help.syncfusion.com/api/js/ejribbon#events:tabclick) and [`tabSelect`](https://help.syncfusion.com/api/js/ejribbon#events:tabselect) events.

{% highlight html %}

	<ej:Ribbon ID="Ribbon" runat="server" Width="800px">
	
		<ApplicationTab MenuItemID="menu" Type="Menu">
	
			<MenuSettings OpenOnClick="false"></MenuSettings>
	
		</ApplicationTab>
	
		<RibbonTabs>
	
			<ej:RibbonTab Id="home1" Text="HOME">
	
				<TabGroupCollection>
	
					<ej:TabGroup Text="Save" AlignType="Columns">
						
						<ContentCollection>
						
							<ej:TabContent>
								
								<ContentGroupCollection>
									
									<ej:ContentGroup Text="Save" Type="Button">
										
										<ButtonSettings Type="Button" ContentType="ImageOnly" PrefixIcon="e-icon e-save" />
									
									</ej:ContentGroup>
								
								</ContentGroupCollection>
							
							</ej:TabContent>
						
						</ContentCollection>
					</ej:TabGroup>
	
				</TabGroupCollection>
	
			</ej:RibbonTab>
			
			<ej:RibbonTab Id="sendrec" Text="Send/Receive">
	
				<TabGroupCollection>
	
					<ej:TabGroup>
						
						<ContentCollection>
							
							<ej:TabContent>
								
								<ContentGroupCollection>
									
									<ej:ContentGroup Text="Save" Type="Custom" ContentID="sendReceive">
									
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
	
		<li><a>FILE</a>
	
			<ul>
	
				<li><a>New</a></li>
	
				<li><a>Open</a></li>
				
		    </ul>			
		
		</li>	
	
	</ul>
	
	<div id="sendReceive">New Tab</div>

{% endhighlight %}

![Tab_images1](Tab_images/Tab_img1.png)