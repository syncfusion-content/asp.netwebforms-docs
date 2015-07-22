---
layout: post
title: AddTab
description: addtab
platform: aspnet
control: Ribbon
documentation: ug
---

# AddTab

This method is used to add tab dynamically in the _Ribbon_ control. This method requires three arguments _addTab(Tabname,TabGroupcollection,index)_

* _Tabname_: Name of the tab.
* _TabGroupcollection_: Collection of the tab groups that tab needs to add.
* _Index_: Index in which the tab is to be added.It is an optional argument. When this argument is not given, by default the tab is added at the last position.



{% highlight html %}



<ej:Ribbon ID="Defaultribbon" runat="server" Width="800">

            <ApplicationTab ItemID="menu" Type="ApplicationMenu">

            </ApplicationTab>

            <RibbonTabs>

                <ej:RibbonTab Id="RibbonTab1" Text="INSERT">

                    <TabGroupCollection>

                        <ej:TabGroup Text="Clipboard">

                            <ContentCollection>

                                <ej:TabContent>

                                    <ContentGroupCollection>



                               <ej:ContentGroup Id="ContentGroup1" Type="Custom" ContentID="paste">

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

<li><a>FILE</a></li>

</ul>

<div id="paste" style="height:40px;width:43px;">Paste</div>

<div id="newtab" style="height:35px;width:43px;">AddTab</div>

<script type="text/javascript">

var ribbonObj;

               var tabGroup = [{

            text: "New", type: "custom", contentID: "newtab"

        }];

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.addTab("AddTab", tabGroup, 2);

});

</script>





{% endhighlight %}





The following screenshot displays the output of the above code example.

![](AddTab_images/AddTab_img1.png)




