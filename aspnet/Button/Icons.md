---
layout: post
title: Icons | Button | ASP.NET Webforms | Syncfusion
description: icons
platform: aspnet
control: Button
documentation: ug
---

# Icons

The Essential Studio provide icons library that contains the number of in-built icons that can be applied for CSS class names to elements and refer **“ej.widgets.all.core.min.css”** file. Use the following syntax to apply class names.

{% highlight css %}

Syntax: .e-icon .e-[icon description]

.e-icon .e-search



{% endhighlight %}

## Adding icon in Button

For example, you can render the desired icon in the button by using the following table that contains the listed icons’ CSS class names in the **“PrefixIcon”** property of button component. Also, use **“ContentType”** property to display the icon in the button. In the following code example, specify the “ContentType” of the button as ImageOnly.    

Refer to the following link to know what are the values passed in the “ContentType” property

<http://help.syncfusion.com/js/api/global>

Also in the button sample, you can use the icon class names as follows,

{% highlight html %}

<ej:Button ID="buttonid" runat="server" Type="Button" ContentType="ImageOnly" PrefixIcon="e-icon e-handup">

</ej:Button>

<ej:SplitButton ID="SplitButton" runat="server" ContentType="ImageOnly" PrefixIcon="e-icon e-calender">

</ej:SplitButton>

<ej:ToggleButton ID="ToggleButton" runat="server" ContentType="ImageOnly" DefaultPrefixIcon="e-icon e-mediaplay"

ActivePrefixIcon="e-icon e-mediapause">

</ej:ToggleButton>



{% endhighlight %}



![](Icons_images/Icons_img1.png)



## List of Icons

The complete list of icons is listed in the following table.

<table>
<tr>
<td>
e-unpin</td><td>
{{ '![](Icons_images/Icons_img2.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-pin</td><td>
{{ '![](Icons_images/Icons_img3.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-upload</td><td>
{{ '![](Icons_images/Icons_img4.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-reload</td><td>
{{ '![](Icons_images/Icons_img5.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-collaps</td><td>
{{ '![](Icons_images/Icons_img6.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-cancel</td><td>
{{ '![](Icons_images/Icons_img7.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-expand</td><td>
{{ '![](Icons_images/Icons_img8.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-minimize</td><td>
{{ '![](Icons_images/Icons_img9.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-login</td><td>
{{ '![](Icons_images/Icons_img10.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-orientationlanscape</td><td>
{{ '![](Icons_images/Icons_img11.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-alignleft</td><td>
{{ '![](Icons_images/Icons_img12.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-aligncenter</td><td>
{{ '![](Icons_images/Icons_img13.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-alignright</td><td>
{{ '![](Icons_images/Icons_img14.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-alignjustify</td><td>
{{ '![](Icons_images/Icons_img15.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-alignnone</td><td>
{{ '![](Icons_images/Icons_img16.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-filterset</td><td>
{{ '![](Icons_images/Icons_img17.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-filternone</td><td>
{{ '![](Icons_images/Icons_img18.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheadup-2x</td><td>
{{ '![](Icons_images/Icons_img19.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheaddown-2x</td><td>
{{ '![](Icons_images/Icons_img20.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheadleft-2x</td><td>
{{ '![](Icons_images/Icons_img21.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheadright-2x</td><td>
{{ '![](Icons_images/Icons_img22.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-numbering</td><td>
{{ '![](Icons_images/Icons_img23.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-bullets</td><td>
{{ '![](Icons_images/Icons_img24.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-maximize</td><td>
{{ '![](Icons_images/Icons_img25.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-delete</td><td>
{{ '![](Icons_images/Icons_img26.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-scroll</td><td>
{{ '![](Icons_images/Icons_img27.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-right-scroll</td><td>
{{ '![](Icons_images/Icons_img28.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-search</td><td>
{{ '![](Icons_images/Icons_img29.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaback</td><td>
{{ '![](Icons_images/Icons_img30.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaforward</td><td>
{{ '![](Icons_images/Icons_img31.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-medianext</td><td>
{{ '![](Icons_images/Icons_img32.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaprev</td><td>
{{ '![](Icons_images/Icons_img33.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaeject</td><td>
{{ '![](Icons_images/Icons_img34.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaclose</td><td>
{{ '![](Icons_images/Icons_img35.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediapause</td><td>
{{ '![](Icons_images/Icons_img36.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-mediaplay</td><td>
{{ '![](Icons_images/Icons_img37.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-righttick</td><td>
{{ '![](Icons_images/Icons_img38.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-smile</td><td>
{{ '![](Icons_images/Icons_img39.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-information</td><td>
{{ '![](Icons_images/Icons_img40.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-left-arrow</td><td>
{{ '![](Icons_images/Icons_img41.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-right-arrow</td><td>
{{ '![](Icons_images/Icons_img42.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-file-delete</td><td>
{{ '![](Icons_images/Icons_img43.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-file-percentage-success</td><td>
{{ '![](Icons_images/Icons_img44.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-file-cancel</td><td>
{{ '![](Icons_images/Icons_img45.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-file-percentage-failed</td><td>
{{ '![](Icons_images/Icons_img46.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-file-retry</td><td>
{{ '![](Icons_images/Icons_img47.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-resize-handle</td><td>
{{ '![](Icons_images/Icons_img48.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-down-arrow</td><td>
{{ '![](Icons_images/Icons_img49.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-time</td><td>
{{ '![](Icons_images/Icons_img50.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-up-arrow</td><td>
{{ '![](Icons_images/Icons_img51.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-date</td><td>
{{ '![](Icons_images/Icons_img52.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-datetime</td><td>
{{ '![](Icons_images/Icons_img53.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-collapse-arrow</td><td>
{{ '![](Icons_images/Icons_img54.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-expand-arrow</td><td>
{{ '![](Icons_images/Icons_img55.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-restore</td><td>
{{ '![](Icons_images/Icons_img56.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-plus</td><td>
{{ '![](Icons_images/Icons_img57.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-minus</td><td>
{{ '![](Icons_images/Icons_img58.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-handup</td><td>
{{ '![](Icons_images/Icons_img59.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-clock</td><td>
{{ '![](Icons_images/Icons_img60.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-cursor</td><td>
{{ '![](Icons_images/Icons_img61.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-hyperlink</td><td>
{{ '![](Icons_images/Icons_img62.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-hyperlinkbreak</td><td>
{{ '![](Icons_images/Icons_img63.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-settings</td><td>
{{ '![](Icons_images/Icons_img64.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-shoppingcart</td><td>
{{ '![](Icons_images/Icons_img65.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-palette</td><td>
{{ '![](Icons_images/Icons_img66.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-warningmessage</td><td>
{{ '![](Icons_images/Icons_img67.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-cut</td><td>
{{ '![](Icons_images/Icons_img68.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-copy</td><td>
{{ '![](Icons_images/Icons_img69.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-paste</td><td>
{{ '![](Icons_images/Icons_img70.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-edit</td><td>
{{ '![](Icons_images/Icons_img71.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-swapleft</td><td>
{{ '![](Icons_images/Icons_img72.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-swapright</td><td>
{{ '![](Icons_images/Icons_img73.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-swapup</td><td>
{{ '![](Icons_images/Icons_img74.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-swapdown</td><td>
{{ '![](Icons_images/Icons_img75.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-zoomin</td><td>
{{ '![](Icons_images/Icons_img76.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-zoomout</td><td>
{{ '![](Icons_images/Icons_img77.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-star</td><td>
{{ '![](Icons_images/Icons_img78.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-home</td><td>
{{ '![](Icons_images/Icons_img79.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-clipboard</td><td>
{{ '![](Icons_images/Icons_img80.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-userlogin</td><td>
{{ '![](Icons_images/Icons_img81.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-dataexport</td><td>
{{ '![](Icons_images/Icons_img82.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheadright</td><td>
{{ '![](Icons_images/Icons_img83.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-arrowheaddown</td><td>
{{ '![](Icons_images/Icons_img84.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-undo</td><td>
{{ '![](Icons_images/Icons_img85.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-redo</td><td>
{{ '![](Icons_images/Icons_img86.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-bold</td><td>
{{ '![](Icons_images/Icons_img87.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-italic</td><td>
{{ '![](Icons_images/Icons_img88.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-underline</td><td>
{{ '![](Icons_images/Icons_img89.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-strikethrough</td><td>
{{ '![](Icons_images/Icons_img90.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-font</td><td>
{{ '![](Icons_images/Icons_img91.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-rarrowdown</td><td>
{{ '![](Icons_images/Icons_img92.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-rarrowleft</td><td>
{{ '![](Icons_images/Icons_img93.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-rarrowup</td><td>
{{ '![](Icons_images/Icons_img94.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-rarrowright</td><td>
{{ '![](Icons_images/Icons_img95.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-calender</td><td>
{{ '![](Icons_images/Icons_img96.png)' | markdownify }}
</td></tr>
<tr>
<td>
e-save</td><td>
{{ '![](Icons_images/Icons_img97.png)' | markdownify }}
</td></tr>
</table>


