---
layout: post
title: Image-Customization | RadialSlider | ASP.NET | Syncfusion
description: Learn here about Image Customization in Syncfusion Essential ASP.NET WebForms RadialSlider Control, its elements, and more.
platform: aspnet
control: RadialSlider
documentation: ug
---
# Image customization in ASP.NET WebForms RadialSlider

## Customizing inner circle 

### Using Class

The **RadialSlider** property **InnerCircleImageClass** allow to set image for the inner circle of the  **RadialSlider**.  By default, the **Radial Slider** innerCircleImageClass is set as "null". Refer to the following code example.

{% tabs %}
{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server" InnerCircleImageClass="customcircle"></ej:RadialSlider>
    
{% endhighlight %}

{% highlight css %}

    <style>
        .customcircle {
            background-image: url("../images/radialslider/diagram.png");
        }
    </style>

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the output of above code.

![ASP.NET WebForms RadialSlider image customization](image-customization_images\image-customization_img1.png)


### Using image URL 

The **RadialSlider** property **InnerCircleImageUrl** allow to set URL image to the inner circle of the **RadialSlider**.  By default, the **Radial Slider** InnerCircleImageUrl  is set as "null". Refer to the following code example.

{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server" InnerCircleImageUrl="../images/radialslider/chevron-right.png"></ej:RadialSlider>

{% endhighlight %}

The following screenshot illustrates the output of above code.

![ASP.NET WebForms RadialSlider image URL ](image-customization_images\image-customization_img2.png)




