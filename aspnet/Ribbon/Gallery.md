---
layout: post
title: Gallery
description: gallery
platform: aspnet
control: Ribbon
documentation: ug
---

# Gallery

The Ribbon control has _Gallery_ support. By using the Galleryin Ribbon, items are displayed with good look and feel and it also enables to classify the items as groups for easy navigation.Gallery can be included in the tabgroups.

To use the _Gallery feature_, include the following properties under tabgroups.

* _Id_ –defines the id of the gallery.
* _Type_- defines the type of the item and it must be of Gallerytype.
* _Columns_ –defines the number of columns to be displayed in a row at intial without gallery expand operation.
* _ExpandedColumns_-defines the number of columns to be displayed in a row at gallery expand operation.
* _ItemHeight_ –defines the height of the  contents.
* _ItemWidth_ –defines the width of contents.
* _GalleryItemCollection_ –defines the collection of the items to be included in the gallery.
* _CustomGalleryItemCollection_ - defines the additional items to be  displayed at gallery expand operation. It can be of CustomItemType Button or Menu. By default value it is Button.

{% highlight html %}

  <ej:Ribbon ID="Ribbon1" runat="server" Width="800">

        <ApplicationTab ItemID="ribbonmenu" Type="ApplicationMenu">

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="RibbonTab1" Text="HOME">

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

                    <ej:TabGroup Text="Gallery">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentGroupCollection>

                                    <ej:ContentGroup Text="Gallery" Type="Gallery" Id="ContentGroup2" Columns="2" ItemHeight="54" ItemWidth="68" ExpandedColumns="3">

<GalleryItemCollection>

                       <ej:GalleryItem Text="Content1" ToolTip="Content1">

                       </ej:GalleryItem >

                       <ej:GalleryItem Text="Content2" ToolTip="Content2">

                       </ej:GalleryItem >

                       <ej:GalleryItem Text="Content3" ToolTip="Content3">

                       </ej:GalleryItem >

                       <ej:GalleryItem Text="Content4" ToolTip="Content4">

                       </ej:GalleryItem >

                       <ej:GalleryItem Text="Content5" ToolTip="Content5">

                       </ej:GalleryItem >

                   </GalleryItemCollection>

                    < CustomGalleryItemCollection >

                        <ej:CustomGalleryItem Text="Save Selection as new quick style" ToolTip="Save" CustomItemType="Button">

                                            </ej:CustomGalleryItem >

                        <ej:CustomGalleryItem CustomItemType="Menu" MenuId="custommenu">

                                            </ej:CustomGalleryItem>

                    </CustomGalleryItemCollection >

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

        <li><a>FILE</a> </li>

    </ul>

<div id="paste" style="height:40px;width:43px;">Paste</div>

    <ul id="custommenu">

        <li><a>New Quick Step</a>



            <ul>

                <li><a>Move to new folder</a></li>

            </ul>

        </li>

    </ul

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Gallery_images/Gallery_img1.png)


![](Gallery_images/Gallery_img2.png)