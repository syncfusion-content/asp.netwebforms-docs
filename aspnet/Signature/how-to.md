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



<ej:Button runat="server" Type="Button" ID="signsave" ClientSideOnClick="onSave" Size="Normal" ShowRoundedCorner="true" Text="Save"></ej:Button>



{% endhighlight %}

Add the following script to define the download format for the canvas

{% highlight js %}


    function onSave() {
            var sign = $("#<%=apisignature.ClientID%>").ejSignature("instance");
            sign.save("MySignature");
        }

{% endhighlight %}

The following screenshot illustrates the Signature with saving (downloading) the drawn image along with its background.

![](how_to_images\savesignatureimagewithuserdefinedformat_img1.png)


## To clear the Signature

To clear the signature, you can simply use the **clear()** method. This method will clear all the drawn strokes in the signature canvas and leaves it empty.

{% highlight html %}

<ej:Signature ID="apisignature" Height="400px" StrokeWidth="3" IsResponsive="true" runat="server"></ej:Signature>

<ej:Button runat="server" Type="Button" ID="signclear" ClientSideOnClick="onclear" Size="Normal" ShowRoundedCorner="true" Text="Clear"></ej:Button>

{% endhighlight %}

{% highlight js %}

<script type="text/javascript">
    function onSave() {
            var sign = $("#<%=apisignature.ClientID%>").ejSignature("instance");
            sign.clear();
        }
 </script>

{% endhighlight %}

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



### To check whether any input to the signature control since render

We can detect whether not there has been any input to the signature control since render. To detect we can use the storeSnap public variable, which is an array that stores all the canvas inputs. At initial rendering this array is empty and we can use this variable to check for the drawn strokes.


{% highlight js %}

   <script type="text/javascript">
      var sign = $("#signature").ejSignature("instance");

            if (ej.isNullOrUndefined(sign.storeSnap)) {
               
                //Something

            }
    </script>   

{% endhighlight %}