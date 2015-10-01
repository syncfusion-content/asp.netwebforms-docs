---
layout: post
title: Appearance and Styling | Ribbon | ASP.NET Webforms | Syncfusion
description: appearance and styling
platform: aspnet
control: Ribbon
documentation: ug
---

# Appearance and Styling

## SelectedItemIndex

Specifies the index of the Ribbon tab to select the given index tab item in the Ribbon control


{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

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

<div id="content">Home control</div>

<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");
ribbonObj.option({ selectedItemIndex: 2 });

});

</script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.



![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)


## DisabledItemIndex

Specifies the index or indexes to disable the corresponding tabs in the Ribbon control.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

<div id="content">Home control</div>



<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.option({ disabledItemIndex: [1, 2] });

});

</script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}













The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)


## EnableItemIndex

Specifies the index or indexes to enable the corresponding tabs in the Ribbon control.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

<div id="content">Home control</div>



<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.option({ disabledItemIndex: [1, 2] });

ribbonObj.option({ enabledItemIndex: [1] });

});

</script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)


## HideTab

This method is used to hide the given text tab in the Ribbon control.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

<div id="content">Home control</div>

<Script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.hideTab("HOME");

});

</Script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)


## ShowTab

This method is used to show the given text tab in the Ribbon control.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

<div id="content">Home control</div>



<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.hideTab("HOME");

ribbonObj.showTab("HOME");

});

</script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)




## RemoveTab

This method is used to remove the given index tab item from the Ribbon control.



{% highlight html %}




<ej:Ribbon ID="Defaultribbon" runat="server" Width="800px">

<ApplicationTab ItemID="menu" Type="ApplicationMenu">

<MenuSettings OpenOnClick="false"></MenuSettings>

</ApplicationTab>

<RibbonTabs>

<ej:RibbonTab Id="insert" Text="INSERT">

<TabGroupCollection>

<ej:TabGroup Text="paste">

<ContentCollection>

<ej:TabContent>

<ContentDefaults Height="70" />

<ContentGroupCollection>

<ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

<ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

</ej:ContentGroup>

</ContentGroupCollection>

</ej:TabContent>

</ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="home" Text="HOME">

<TabGroupCollection>

<ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

<div id="content">Home control</div>



<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.removeTab(2);

});

</script>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)


## Width

Specifies the Width to the Ribbon control.



{% highlight html %}





<ej:Ribbon ID="Defaultribbon" runat="server" Width="800">

        <ApplicationTab ItemID="menu" Type="ApplicationMenu">

            <MenuSettings OpenOnClick="false"></MenuSettings>

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="insert" Text="INSERT">

                <TabGroupCollection>

                    <ej:TabGroup Text="paste">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentDefaults Height="70" Width="50" />

                                <ContentGroupCollection>

                                    <ej:ContentGroup Id="paste" Text="Paste" ToolTip="Paste" Type="Button" IsBig="true">

                                        <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

                                    </ej:ContentGroup>

                                </ContentGroupCollection>

                            </ej:TabContent>

                        </ContentCollection>

                    </ej:TabGroup>

                </TabGroupCollection>

            </ej:RibbonTab>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="New" Type="custom" AlignType="Columns" ContentID="content">

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

    <div id="content">Home control</div>

<style type="text/css">

.e-ribbon .e-ribbonpaste:before {

content: "\e645";

font-size: 36px;

position: relative;

left: -9px;

top: -4px;

}

</style>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)




## Add Tab Group

This method is used to add Ribbon Group dynamically in the Ribbon control. This method needs three arguments addTabGroup(Tab index, Groupcollection, Group index)

Tab index : Index of tab, where the group is to be added.

TabGroup collection : Collection of the groups that group needs to add.

Group Index : Index of ribbon group, where the group is to be added. It is optional argument, when this argument is not given, group is added at last position by default.



{% highlight html %}





<ej:Ribbon ID="Ribbon" ClientIDMode="Static" runat="server" Width="100%">

        <ApplicationTab ItemID="menu" Type="ApplicationMenu"/>

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="New" AlignType="rows">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentGroupCollection>

                                    <ej:ContentGroup Id="one" Text="one" ToolTip="one" Type="Button">

                                    </ej:ContentGroup>

                                    <ej:ContentGroup Id="two" Text="two" ToolTip="two" Type="Button">

                                    </ej:ContentGroup>

                                </ContentGroupCollection>

                                <ContentDefaults Width="60" Height="70" Type="Button" />

                            </ej:TabContent>

                        </ContentCollection>

                    </ej:TabGroup>

                </TabGroupCollection>

            </ej:RibbonTab>

        </RibbonTabs>

    </ej:Ribbon>

<ul id="menu">

<li><a>FILE</a></li>

</ul>

<script type="text/javascript">

var ribbonGrp = {

        text: "New", alignType: ej.Ribbon.alignType.rows, content: [{

            groups: [{

                id: "new",

                text: "New"

            }],

            defaults: {

                type: ej.Ribbon.type.button,

                width: 60,

                height: 70

            }

        }]

    };

$(function(){

         var ribbonObj = $("#Ribbon").data("ejRibbon");

            // Add new ribbon group with given list

            ribbonObj.addTabGroup(1, ribbonGrp, 0);

        })

</script>





{% endhighlight %}



The following output is displayed as a result of the above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)


## Add Tab Group Content

This method is used to add group content dynamically in the ribbon. This method contains five arguments addTabGroupContent(Tab index, Group index, Subgroup index, Content, Content index)

Tab index : Ribbon Tab index.

Group index : Ribbon group index.

Subgroup Index : Sub group index. Content to be added belongs to this sub group index.

Content : Collection of the group content that is added as Ribbon group content. 

Content Index : Ribbon content index, this is optional argument. When this argument is not given, the Group content is added at last position by default.



{% highlight html %}





<ej:Ribbon ID="Ribbon" ClientIDMode="Static" runat="server" Width="100%">

        <ApplicationTab ItemID="ribbonmenu" Type="ApplicationMenu"/>

        <RibbonTabs>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="New" AlignType="rows">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentGroupCollection>

                                    <ej:ContentGroup Id="one" Text="one" ToolTip="one" Type="Button">

                                    </ej:ContentGroup>

                                    <ej:ContentGroup Id="two" Text="two" ToolTip="two" Type="Button">

                                    </ej:ContentGroup>

                                </ContentGroupCollection>

                                <ContentDefaults Width="60" Height="70" Type="Button" />

                            </ej:TabContent>

                        </ContentCollection>

                    </ej:TabGroup>

                </TabGroupCollection>

            </ej:RibbonTab>

        </RibbonTabs>

    </ej:Ribbon>

<ul id="menu">

<li><a>FILE</a></li>

</ul>

<script type="text/javascript">

var content = {

        id: "new",

        text: "new",

    };

$(function(){

         var ribbonObj = $("#Ribbon").data("ejRibbon");

            // Add new ribbon group with given list

         ribbonObj.addTabGroupContent(1,0,0,content,2);

        })

</script>



{% endhighlight %}



The following output is displayed as a result of the above code example.

![C:/Users/ApoorvahR/Desktop/1.png](Appearance-and-Styling_images/Appearance-and-Styling_img9.png)





