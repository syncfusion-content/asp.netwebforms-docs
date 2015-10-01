---
layout: post
title: Custom Tooltip | Ribbon | ASP.NET Webforms | Syncfusion
description: custom tooltip
platform: aspnet
control: Ribbon
documentation: ug
---

# Custom Tooltip

The Ribbon control has Custom Tooltip support that is displayed when you move the mouse over the control elements. You can define the CustomTooltip under the ContentGroup, GalleryItem, and CustomGalleryItem etc... CustomTooltip contains Title, Content, PrefixIcon properties that are used to set Title, Content and placing the icon into this.



{% highlight html %}




  <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%">

     <ApplicationTab ItemID="ribbonmenu" Type="ApplicationMenu">

     </ApplicationTab>

  <RibbonTabs>

     <ej:RibbonTab Id="home" Text="HOME">

        <TabGroupCollection>

        <ej:TabGroup Text="Clipboard" AlignType="Columns">

           <ContentCollection>

           <ej:TabContent>

              <ContentGroupCollection>

                <ej:ContentGroup Id="paste">

                 <ButtonSettings ContentType="ImageOnly" PrefixIcon="e-ribbon e-ribbonpaste" />

 <CustomToolTip Content="<h6> Paste the content.<br/><br/>Add content on the Clipboard to your document. </h6>" Title="Paste" PrefixIcon="e-pastetip" />

                </ej:ContentGroup>

              </ContentGroupCollection>

           </ej:TabContent>

           </ContentCollection>

        </ej:TabGroup>

      </TabGroupCollection>

    </ej:RibbonTab>

  </RibbonTabs>

 </ej:Ribbon>



 <ul id="ribbonmenu">

                <li><a>FILE</a>

                    <ul>

                        <li><a>New</a></li>

                    </ul>

                 </li>

  </ul>



{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Custom-Tooltip_images/Custom-Tooltip_img1.png)


