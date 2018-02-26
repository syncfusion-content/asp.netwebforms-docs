---
layout: post
title: Image Customization | RadialMenu | ASP.NET Webforms | Syncfusion
description: image customization
platform: aspnet
control: Radial Menu
documentation: ug
---

## Image Customization

You can customize the **Radial Menu’s** Center and Back images by using the **ImageClass** and **BackImageClass** properties. Every menu item can be added with image using **url** property. By using this **ImageClass** attribute, you can customize the **Radial Menu** center image. 

Sub-Items are also supported in the **Radial Menu**. To navigate Sub-Items, click the arrows in the outer ring and it displays the corresponding sub-items group. Clicking the center button when a sub-items group is shown, displays the items on the previous level. Nested **Radial Menu** has the second level back button. In this case, you can use the **BackImageClass** attribute to change your second level back button. **BackImageClass** is used to customize the **nestedRadialmenu** back image. Refer to the following code example.

You can add the page content with text-area by referring to this section.

{% highlight html %}

    <ej:RadialMenu ID="nestedRadialMenu" runat="server" ImageClass="imageclass" BackImageClass="backimageclass" TargetElementId="radialTargetTwo" ClientSideOnClick="click">
                <Items>
                    <ej:RadialMenuItems Text="Copy" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png">
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Font" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/font.png">
                        <Items>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/f1.png" Text="Italic" ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/font.png" Text="Bold" ></ej:RadialMenuItems>
                        </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Table" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/table.png" ></ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="List" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/list.png" >
                        <Items>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l1.png" Text="List" ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l2.png" Text=" List " ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l3.png" Text=" List " ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l4.png" Text=" List " ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l5.png" Text=" List " ></ej:RadialMenuItems>
                        </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Paste" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png">
                        <Items>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/c1.png" Text="Paste" ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/c2.png" Text="Paste" ></ej:RadialMenuItems>
                        </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Sort" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/sort.png">
                        <Items>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/s1.png" Text="Sort" ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/s2.png" Text="Sort" ></ej:RadialMenuItems>
                        </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Alignment" ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/align.png" >
                        <Items>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a1.png" Text="Left" ></ej:RadialMenuItems>
                            <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a2.png" Text="Right" ></ej:RadialMenuItems>
                        </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems Text="Draw" ImageURL="asp.syncfusion.com/demos/web/Contentt/images/RadialMenu/draw.png" >
                    </ej:RadialMenuItems>
                </Items>
            </ej:RadialMenu>
    
    
{% endhighlight %}

Add the following script in your code.
    
{% highlight javascript %}

            function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 150, radialDiameter = 2 * radialRadius,
                // To get Iframe positions
                iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
                // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
                $('#<%=nestedRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
            }
        
{% endhighlight %}

Add the following styles in your code.
    
{% highlight css %}

    <style type="text/css" class="cssStyles">
        .e-radialmenu .imageclass {
            background-image: url(http://js.syncfusion.com/UG/web/Content/radial/main.png);
        }

        .e-radialmenu .backimageclass {
            background-image: url(http://js.syncfusion.com/UG/web/Content/radial/Back_button.png);
        }
    </style>


{% endhighlight %}



The following screenshot illustrates the output.

![](image-customization_images\image-customization_img1.png)

Radial Menu - Image Customization – Main menu
{:.caption}

When you click the arrow, it navigates to the child item as illustrated in the following screenshot.

![](image-customization_images\image-customization_img2.png)

Radial Menu- Image Customization – Child menu 
{:.caption}




