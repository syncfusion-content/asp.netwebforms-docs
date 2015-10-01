---
layout: post
title: Controls Support | Ribbon | ASP.NET Webforms | Syncfusion
description: controls support
platform: aspnet
control: Ribbon
documentation: ug
---

# Controls Support

In Ribbon control, Button,SplitButton,DropDownList Toggle button,Custom controls provide support to the groups.

* Type property is used to define the controls.



* SplitButton - to add Split button control.



* Button - to add Button control.



* DropDownList - to add Dropdown List control.



* ToggleButton - to add Toggle button control.



* Custom - to add custom controls.

The default type is Button.

{% tabs %}

{% highlight html %}




<ej:Ribbon ID="defaultRibbon" runat="server" Width="800px" ClientSideOnCreate="createControl">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="Split Button" AlignType="Columns">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Width="50" Height="65" Type="Button" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" ToolTip="Paste" Type="SplitButton">

<SplitButtonSettings ButtonMode="Dropdown" ArrowPosition="Bottom" TargetID="pasteul"  ContentType="TextAndImage" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="DropDown List" AlignType="Rows">

<ContentCollection>

<ej:TabContent>

<ContentGroupCollection>

<ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">

<DropdownSettings Value="1" Text="Fonts" Width="150"></DropdownSettings>

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="Custom" Type="rows">

<ContentCollection>

<ej:TabContent>

<ContentGroupCollection>

<ej:ContentGroup Id="fontcolor" Text="Font Color" ToolTip="Font Color" Type="Custom" ContentID="fontcolor">

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="Button" AlignType="Rows">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Type="Button" Height="70" Width="45" />

<ContentGroupCollection>

<ej:ContentGroup Id="undo" Text="Undo" ToolTip="Undo" IsBig="false">

<ButtonSettings ContentType="TextAndImage" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-undo" Type="Reset" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="Toggle" AlignType="Rows">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Type="ToggleButton" Height="70" Width="40" />

<ContentGroupCollection>

<ej:ContentGroup Id="bold" Text="Bold" ToolTip="Bold">

<ToggleButtonSettings ContentType="ImageOnly" DefaultText="Bold" ActiveText="Bold" DefaultPrefixIcon="e-ribbon e-bold" ActivePrefixIcon="e-ribbon e-bold"/>

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>



</RibbonTabs>

</ej:Ribbon>



</div>

<ul id="menu">

<li><a>FILE</a>

<ul>

<li><a>New</a></li>

<li><a>Open</a></li>

<li><a>Save</a></li>

<li><a>Save as</a></li>

<li><a>Print</a></li>

</ul>

</li>

</ul>

<ul id="pasteul">

<li><a>Paste</a></li>

</ul>

<input id="fontcolor"/>



<style>

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}



.e-ribbon .e-undo:before {

content: "\e736";

font-size: 28px;

position: relative;

left: -7px;

top: -4px;

}



.e-ribbon .bold:before {

content: "\e636";

}



.e-ribbon .e-fontcoloricon:before {

content: "\e632";

font-size: 15px;

position: relative;

right: 10px;

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

The following output is displayed as a result of the above code example.

![](Controls-Support_images/Controls-Support_img1.png)


