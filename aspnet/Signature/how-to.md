---
layout: post
title: How To
description: How To
platform: aspnet
control: Signature
documentation: ug
---

# How To

## Save signature image with user defined format

By default, the downloaded image from the signature canvas will be in **png** format. We can define our own format to download the image with **SaveImageFormat** property. And we can also save the image along with the background by using the **SaveWithBackground** property.

In the ASPX page, define the following code.

{% highlight html %}

<ej:Signature ID="apisignature" Height="400px" StrokeWidth="3" BackgroundImage="../Content/images/progressbar/water.png" SaveWithBackground="true" IsResponsive="true" SaveImageFormat="jpg"  runat="server"></ej:Signature>



<ej:Button runat="server" Type="Button" ID="signsave" ClientSideOnClick="onsave" Size="Normal" ShowRoundedCorner="true" Text="Save"></ej:Button>



{% endhighlight %}

Add the following script to define the download format for the canvas

{% highlight js %}


    function onsave() {
            var sign = $("#<%=apisignature.ClientID%>").ejSignature("instance");
            sign.save("MySignature");
        }

{% endhighlight %}

The following screenshot illustrates the Signature with saving (downloading) the drawn image along with its background.

![](how_to_images\savesignatureimagewithuserdefinedformat_img1.png)


## Make signature as responsive

When the signature control is resized or even the window is resized the strokes drawn in the signature will be disappeared. To make the strokes visible even after resizing the window, we must set the **IsResponsive** property as true.

In the ASPX page, define the following code.

{% highlight html %}

<ej:Signature ID="signature" IsResponsive="true" runat="server"></ej:Signature> 

{% endhighlight %}

The following screenshot illustrates the Signature with responsiveness.

Before Responsiveness:

![](how_to_images\makesignatureasresponsive_img1.png)

After giving the Responsiveness:

![](how_to_images\makesignatureasresponsive_img2.png)



