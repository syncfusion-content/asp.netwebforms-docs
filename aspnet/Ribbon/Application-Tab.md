---
layout: post
title: Application-Tab
description: application tab
platform: aspnet
control: Ribbon
documentation: ug
---

## Application Tab

The_application menu_ support is provided in the _Ribbon_ control _ApplicationTab_. Use _ApplicationTab_ property to define the application tab with menu. In _ApplicationTab_ definition, _Type_ property defines the application menu and the value is _ApplicationMenu_,_ItemID_ property to specify ID of UL list for application menu and _MenuSettings_ tag to specify all the members and events of the menu.



{% highlight html %}

[ASP]

[Aspx]



<ej:Ribbon ID="Ribbon" runat="server" Width="800px”>

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



The following screenshot illustrates _Ribbon_ with application menu.

{ ![](Application-Tab_images/Application-Tab_img1.png) | markdownify }
{:.image }


