---
layout: post
title: Collapse and Expand | Ribbon | ASP.NET Webforms | Syncfusion
description: collapse and expand
platform: aspnet
control: Ribbon
documentation: ug
---

# Collapse and Expand

## Collapse

Collapse method is used to minimize the ribbon control tab contents.You can minimize the Ribbon tab content by using the client side method collapse().



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

<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.collapse();

});

</script>







{% endhighlight %}





The following screenshot displays the output of the above code example.

![](Collapse-and-Expand_images/Collapse-and-Expand_img1.png)


## Expand



Expand method is used to expand the minimized ribbon control tab contents.You can expand the Ribbon tab content by using the client side method expand() .



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

<script type="text/javascript">

var ribbonObj;

$(function()

{

ribbonObj = $("#Defaultribbon").data("ejRibbon");

ribbonObj.expand();

});

</script>





{% endhighlight %}



The following screenshot displays the output of the above code example.

![](Collapse-and-Expand_images/Collapse-and-Expand_img2.png)


