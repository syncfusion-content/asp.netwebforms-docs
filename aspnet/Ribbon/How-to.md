---
layout: post
title: Get Ribbon object | Ribbon | ASP.NET Webforms | Syncfusion
description: get ribbon object
platform: aspnet
control: Ribbon
documentation: ug
---

# How to

## Get Ribbon object

After Ribbon initialization, Ribbon object is stored in a container element of Ribbon. To access Ribbon object, you can use the following code example.

{% highlight js %}

var ribbonObject = $("#Ribbon").ejRibbon("instance");

[or]

var ribbonObject = $("#Ribbon").data("ejRibbon");

{% endhighlight %}

## Insert own image in Ribbon

Own images can be inserted in Ribbon by rendering button with "TextAndImage" or "Image" `contentType` with required icon classes. Refer to the following code example. 

{% highlight HTML %}
 
    <ej:Ribbon ID="Ribbon1" runat="server" Width="100%">
             <ApplicationTab MenuItemID="menu" Type="Menu">
                    <MenuSettings OpenOnClick="false"></MenuSettings>               
                 </ApplicationTab>
                 <RibbonTabs>
                         <ej:RibbonTab ID="Home" Text="Home">
                             <tabgroupcollection>
                                    <ej:TabGroup ID="Tab" Text="Alignment" AlignType="Rows">
                                        <contentcollection>
                                            <ej:TabContent>
                                                <ContentGroupCollection>
                                                     <ej:ContentGroup Id="Dos" Text="dossier">
                                                        <ButtonSettings ContentType="TextAndImage" PrefixIcon="e-icon .e-dos"  Type="Button" />
                                                    </ej:ContentGroup>
                                                    <ej:ContentGroup Id="Act" Text="acties">
                                                        <ButtonSettings ContentType="TextAndImage" PrefixIcon=" e-icon .e-act" Type="Button" />
                                                    </ej:ContentGroup>
                                                </ContentGroupCollection>
                                            </ej:TabContent>
                                        </contentcollection>
                                    </ej:TabGroup>
                             </tabgroupcollection>
                        </ej:RibbonTab>
                 </RibbonTabs>
        </ej:Ribbon>

{% endhighlight %}

Add required background image for this icon class

{% highlight CSS %}
  
       .e-dos{
            background-image: url("../Content/ej/web/common-images/ribbon/User.jpg");
            background-repeat:no-repeat;
            height: 32px;
            width: 32px;
         }
       .e-act{
            background-image: url("../Content/ej/web/common-images/ribbon/Version.png");
            background-repeat:no-repeat;
            height: 32px;
            width: 32px;
         }

{% endhighlight %}

Sample can be downloaded [here](https://www.syncfusion.com/downloads/support/directtrac/246015/ze/Ribbon-icon-633927069)