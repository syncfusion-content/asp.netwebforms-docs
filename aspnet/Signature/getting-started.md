---
layout: post
title: getting started
description: getting started
platform: aspnet
control: Signature
documentation: ug
---

# Getting Started

The Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature using mouse or touch.

This section helps to understand the getting started of the Signature widget with the step-by-step instructions. The following screenshot demonstrates the functionality of Signature widget.

![](getting_started_images\gettingstarted_img1.png)


## Creating your first Signature in ASP application

Create an ASP Project and add the necessary DLL’s and scripts with the help of the given [ASP Getting Started](http://help.syncfusion.com/aspnet/getting-started) documentation.

Initialize the corresponding Signature control in the ASPX page with the below code.

{% highlight html %}

 <div class="control">
                <ej:Signature ID="signature" Height="400px" StrokeWidth="3" IsResponsive="true" runat="server"></ej:Signature>
        </div>

{% endhighlight %}

Execute the code to render a Signature widget as follows.

![](getting_started_images\gettingstarted_img2.png)


## Adjusting Signature Size

We can customize the width and height of the Signature by width and height properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature control with customized width and height.

{% highlight html %}

<ej:Signature ID="signature" Height="500px" width="200px" runat="server"></ej:Signature>

{% endhighlight %}

The following screenshot illustrates signature with customized width and height.

![](getting_started_images\gettingstarted_img3.png)





