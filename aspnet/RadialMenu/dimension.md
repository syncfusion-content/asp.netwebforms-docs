---
layout: post
title: Dimension | Radial Menu | ASP.NET Webforms | Syncfusion
description: dimension
platform: aspnet
control: Radial Menu
documentation: ug
---


## Dimension

You can customize **Radial Menu** dimension by using **Radius** and **Position** properties.

### Radius

You can customize the **Radial Menu** size by using the **Radius** property. By default, the **Radial Menu** Radius is set as 150px. Refer to the following code example.

{% highlight html %}

        <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" Radius="200" >         
            <Items>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/font.png" Text="Bold" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/f1.png" Text="Italic" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/align.png" Text="Align" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/sort.png" Text="Sort" ></ej:RadialMenuItems>
            </Items>
        </ej:RadialMenu>
    
{% endhighlight %}

Add the following script in your code.
    
{% highlight javascript %}

        function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 200, radialDiameter = 2 * radialRadius,
                // To get Iframe positions
                iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
                // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
                $('#<%=defaultRadialMenu.ClientID%>').ejRadialMenu("setPosition", x, y);
         }

{% endhighlight %}


The following screenshot illustrates the **Radial Menu** while clicking on the settings icon.

![](dimension-images\dimension_img2.png)

### Position 

To display the **Radial Menu** in the web page in a specific area, we can use the **Position** property. By default, the **Radial Menu** Position is set as null. 

Refer to the following code example.

{% highlight html %}

      <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne">      
            <Position X="10" Y="10" />   
            <Items>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" ></ej:RadialMenuItems>
            </Items>
        </ej:RadialMenu>
    

{% endhighlight %}

Add the following script in your code.
    
{% highlight javascript %}

        function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 150, radialDiameter = 2 * radialRadius,
                // To get Iframe positions
                iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,              
         }

{% endhighlight %}


The following screenshot illustrates the output while selecting the text in the page.

![](dimension-images\dimension_img4.png)

