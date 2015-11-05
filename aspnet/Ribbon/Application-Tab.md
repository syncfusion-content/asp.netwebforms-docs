---
layout: post
title: Application Tab | Ribbon | ASP.NET Webforms | Syncfusion
description: application tab
platform: aspnet
control: Ribbon
documentation: ug
---

# Application Tab

The application menu support is provided in the Ribbon control  ApplicationTab. Use ApplicationTab property to define the application tab with menu. In ApplicationTab definition, Type property defines the application menu and the value is ApplicationMenu,ItemID property to specify ID of UL list for application menu and MenuSettings tag to specify all the members and events of the menu.



{% highlight html %}





<ej:Ribbon ID="Ribbon" runat="server" Width="800px”>

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



{% endhighlight %}



The following screenshot illustrates Ribbon with application menu.

![](Application-Tab_images/Application-Tab_img1.png)


