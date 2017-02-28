---
layout: post
title: signature customization
description: signature customization
platform: aspnet
control: Signature
documentation: ug
---

# Signature Customization

## Background color

Signature widget allows you to set the background Color for the control using the **BackgroundColor** property. When we set our required background, then the signature’s background color will be changed automatically.

The following code example is used to render the Signature control with background color

In the ASPX page, define the following code.

{% highlight html %}

<ej:Signature ID="signature" BackgroundColor="grey" runat="server"></ej:Signature>

{% endhighlight %}

The following screenshot illustrates the Signature with custom defined background color

![](signature_customization_images\backgroundcolor_img1.png)

## Background Image

Signature widget allows you to set the background image for the control using the **BackgroundImage** property. When we set our required background image, then the signature’s canvas will be changed with the given image.

The following code example is used to render the Signature control with customized background image.

In the ASPX page, define the following code.

{% highlight html %}

<ej:Signature ID="signature" BackgroundImage="image.jpg" runat="server"></ej:Signature>

{% endhighlight %}

The following screenshot illustrates the Signature with custom defined background image.

![](signature_customization_images\backgroundimage_img1.png)


## Stroke color

Signature widget allows you to set the stroke color for the signature stroke using the **StrokeColor** property. When we set our required color, then the signature’s stroke color will be changed.

The following example is used to render the Signature control with customized stroke color.

In the ASPX, define the following code.

{% highlight html %}

<ej:Signature ID="signature" StrokeColor="red" runat="server"></ej:Signature>

{% endhighlight %}

The following screenshot illustrates the Signature with custom defined stroke color.

![](signature_customization_images\strokecolor_img1.png)


## Stroke Width

Signature widget allows you to set the stroke width using the **StrokeWidth** property. When we set our required width, then the signature’s stroke width will be changed.

The following code example is used to render the Signature control with maximum stroke width value.

In the ASPX page, define the following code to render signature with maximum stroke width value.

{% highlight html %}

<ej:Signature ID="signature" StrokeWidth="5" runat="server"></ej:Signature>

{% endhighlight %}

The following screenshot illustrates the Signature with custom defined stroke maximum value.

![](signature_customization_images\strokewidth_img1.png)

