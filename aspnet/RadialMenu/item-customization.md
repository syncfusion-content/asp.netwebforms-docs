---
layout: post
title: Item-Customization | Radial Menu | ASP.NET Webforms | Syncfusion
description: item customization
platform: aspnet
control: Radial Menu
documentation: ug
---

## Item Customization

You can customize individual **Radial Menu** items by using the items properties.

### Adding image and text to RadialMenu items

The **ImageUrl** property specifies the URL of the image for the items. **Text** attribute is used to specify the item text. Refer to the following code example.

You can add the page content in RTE control by referring this section.

{% highlight html %}


     <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" >         
            <Items>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste"></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" ></ej:RadialMenuItems>
            </Items>
     </ej:RadialMenu>    
    
{% endhighlight %}

You can display the **Radial Menu** by performing desired action on the target content while selecting the text inside the target. Therefore, call the **radialShow** method in the select action of the content. Refer the following code example and add it to the script.
    
{% highlight javascript %}
      
        function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            $('#<%=defaultRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
        }                           


{% endhighlight %}



The following screenshot illustrates the output.

![](item-customization_images\item-customization_img1.png)

### Adding events to Radial Menu items

You can specify the click event to corresponding image/text of **Radial Menu** items for performing some specific action. You need to handle the click event in script manually for each item click.

You can add the page content in RTE control by referring to this section

{% highlight html %}


        <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" >         
                <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" Click="copy"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/Font_letter.png" Text="Font"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/list.png" Text="List" >
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/list.png" Text="List" ></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l5.png" Text="List" ></ej:RadialMenuItems>
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/bold.png" Text="Bold" Click="bold">
                        <Items>                
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/f1.png" Text="Italic" Click="italic"> </ej:RadialMenuItems>              
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/font.png" Text="Bold" Click="bold"> </ej:RadialMenuItems>             
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" Enabled="false">
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" Enabled="false"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" Enabled="false"></ej:RadialMenuItems>
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/align.png" Text="Alignment">
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a1.png" Text="Left"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a2.png" Text="Right"></ej:RadialMenuItems>
                    </Items>
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
            $('#<%=defaultRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
        }              
        function italic(e) {
            rteObj.executeCommand("italic");
        }
        function bold(e) {
            rteObj.executeCommand("bold");
        }
        function copy(e) {
            rteObj.executeCommand("copy");
        }


{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img2.png)

### Badge Customization in Radial Menu Items

You can specify set badges for the items by using badge settings in radial menu. You can set value for badge and enable badge with default value.

The **Enabled** property to enable or disable badges. **Value** attribute is to set the badge value.

{% highlight html %}


        <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" >         
                <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" >
                    <Badge Enabled="true" Value="3" /></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" ></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" ></ej:RadialMenuItems>
                </Items>
        </ej:RadialMenu>    
    
{% endhighlight %}

You can display the **Radial Menu** by performing desired action on the target content while selecting the text inside the target. Therefore, call the **radialShow** method in the select action of the content. Refer the following code example and add it to the script.
    
{% highlight javascript %}
      
        function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            $('#<%=defaultRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
        }                           


{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img3.png)

### Slider support for Radial Menu Items

You can customize the Radial Menu with slider settings.The **data-ej-type** property specifies the type of radial menu item, where you can set the type for RadialMenu item.

You can customize the **Radial Menu** slider settings by using the **Ticks**, **StrokeWidth** and **LabelSpace** properties. The **Ticks** property specifies the slider ticks for radial menu item.**StrokeWidth** attribute is used to specify the slider's stroke width value.**LabelSpace** attribute is used to specify the value of slider label space.

Refer to the following code example.

You can add SliderSettings in radial menu items by referring this section.

{% highlight html %}


        <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" >         
                <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" Click="copy"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/Font_letter.png" Text="Font" Type="Slider">
                    <SliderSettings StrokeWidth="2" Ticks="[0, 2, 4, 6, 8, 10, 12, 14]" /> 
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/list.png" Text="List" >
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/list.png" Text="List" ></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/l5.png" Text="List" ></ej:RadialMenuItems>
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/bold.png" Text="Bold" Click="bold">
                        <Items>                
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/f1.png" Text="Italic" Click="italic"> </ej:RadialMenuItems>              
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/font.png" Text="Bold" Click="bold"> </ej:RadialMenuItems>             
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" Enabled="false">
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" Enabled="false"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" Enabled="false"></ej:RadialMenuItems>
                    </Items>
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/align.png" Text="Alignment">
                    <Items>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a1.png" Text="Left"></ej:RadialMenuItems>
                    <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/a2.png" Text="Right"></ej:RadialMenuItems>
                    </Items>
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
            $('#<%=defaultRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
        }                      

{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img4.png)