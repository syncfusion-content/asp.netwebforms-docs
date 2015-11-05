---
layout: post
title: Group Expander | Ribbon | ASP.NET Webforms | Syncfusion
description: group expander
platform: aspnet
control: Ribbon
documentation: ug
---

# Group Expander

The Ribbon control has group expander support. Set EnableGroupExpander value to true to enable the group expander for each group in the ribbon tab. The event for group expander is GroupExpand.

{% tabs %}

{% highlight html %}


<ej:Ribbon ID="Ribbon" runat="server" Width="800px">

<ApplicationTab MenuItemID="menu" Type="Menu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Columns" EnableGroupExpander="true">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Width="100" />

<ContentGroupCollection>

<ej:ContentGroup Text="New" Id="new" ToolTip="New" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-new" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="Font" AlignType="Rows">

<ContentCollection>

<ej:TabContent>

<ContentGroupCollection>

<ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">

<DropdownSettings Value="Segoe UI" Text="Fonts" Width="150"></DropdownSettings>

</ej:ContentGroup>

<ej:ContentGroup Id="fontsize" ToolTip="FontSize" Type="DropDownList">

<DropdownSettings Value="1pt" Width="65"></DropdownSettings>

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

<ej:TabContent>

<ContentGroupCollection>

<ej:ContentGroup Id="bold" Text="Bold" ToolTip="Bold">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon bold" Click="executeAction" />

</ej:ContentGroup>

<ej:ContentGroup Id="italic" Text="Italic" ToolTip="Italic" EnableSeparator="true">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonitalic" />

</ej:ContentGroup>

<ej:ContentGroup Id="underline" Text="Underline" ToolTip="Underline">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonunderline" />

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

<ul id="menu">

<li><a>FILE</a>

<ul>

<li><a>New</a></li>

<li><a>Open</a></li>

</ul>

</li>

</ul>



<style type="text/css">

.e-ribbon .e-new:before {

content: "\e646";

font-size: 36px;

position: relative;

left: -12px;

top: -4px;

}

.e-ribbon .e-ribbonitalic:before {

content: "\e635";

}



.e-ribbon .bold:before {

content: "\e636";

}

.e-ribbon .e-ribbonunderline:before {

content: "\e634";

}

</style>



{% endhighlight %}



{% highlight c# %}





protected void Page_Load(object sender, EventArgs e)

{

List<FontFamily> fontlist = new List<FontFamily>();

fontlist.Add(new FontFamily(1, "Segoe UI"));

fontlist.Add(new FontFamily(2, "Arial"));

fontlist.Add(new FontFamily(3, "Times New Roman"));

fontlist.Add(new FontFamily(4, "Tahoma"));

fontlist.Add(new FontFamily(5, "Helvetica"));

this.fontfamily.DropdownSettings.DataSource = fontlist;

}

[Serializable]

class FontFamily

{

public int value { get; set; }

public string text { get; set; }

public FontFamily(int cvalue, string ctext)

{

this.value = cvalue;

this.text = ctext;

}

}



{% endhighlight %}

{% endtabs %}



The following screenshot illustrates the group New with the group expander.

![](Group-Expander_images/Group-Expander_img1.png)


