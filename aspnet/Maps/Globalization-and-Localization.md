---
layout: post
title: Map Elements | Maps | ASP.NET Webforms | Syncfusion
description: map elements
platform: aspnet
control: Maps
documentation: ug
---

# RTL

Right-to-Left or RTL describes the ability of application to handle and responds you to communicate with a right-to-left language, such as Arabic or Japanese. enableRTL property is used to change the rendering format to “Right-to-Left”. By default, legend and tooltip will be rendered as “Left-to-Right” in Maps.

{% highlight html %}



    <ej:Map ID="map" runat="server" EnableRTL="true" >    

    </ej:Map>



{% endhighlight %}


In default legend, after setting `EnableRTL` is set as true, legend text will be rendered first, and then legend icon will be rendered. 

![](Globalization-and-Localization_images/Globalization-and-Localization_images1.png)

## Interactive legend

If `EnableRTL` is set as true, then whole interactive legend will be rendered from right-to-left, which means left label will be rendered at right side, and right label will be rendered at left side. Also, navigation arrow position will be changed to right side.

![](Globalization-and-Localization_images/Globalization-and-Localization_images2.png)

## Tooltip

If `EnableRTL` is set as true, tooltip will be rendered at the left side of the mouse cursor. 

![](Globalization-and-Localization_images/Globalization-and-Localization_images3.png)
