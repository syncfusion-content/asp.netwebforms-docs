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

By default, the downloaded image form the signature canvas will be in **png** format. We can define our own format to download the image with **SaveImageFormat** property. And we can also save the image along with the background by using the **SaveWithBackground** property.

In the ASPX page, define the following code.

{% highlight html %}

<ej:Signature ID="apisignature" Height="400px" StrokeWidth="3" BackgroundImage="../Content/images/progressbar/water.png" SaveWithBackground="true" IsResponsive="true" runat="server"></ej:Signature>

<a id="download">

 <input id="signsave" class="e-btn" type="button" value="Save" />

</a> 

{% endhighlight %}

Add the following script to define the download format for the canvas

{% highlight js %}

   $(function () {

   $("#signsave").ejButton({
                size: "normal",
                showRoundedCorner: true,
            });

            var clientPng = document.getElementById('download');
            if (clientPng.addEventListener)
                clientPng.addEventListener('click', downloadClient, false);
            else
                clientPng.attachEvent('onclick', downloadClient, false);

            function downloadClient(e) {
                var sign = $("#<%=apisignature.ClientID%>").ejSignature("instance");

                this.download = "Signature." + sign.model.saveImageFormat + "";
                var div = $("#<%=apisignature.ClientID%>");
                var canvas = div["children"]()[0];
                this.href = canvas.toDataURL("image/" + sign.model.saveImageFormat + "", 1.0);
            } });

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



