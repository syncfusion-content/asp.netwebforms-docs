---
layout: post
title: Sparkline Dimensions in ASP.NET Sparkline Control | Syncfusion
description: Learn here about Sparkline Dimensions in Syncfusion Essential ASP.NET WebForms Sparkline Control, its elements, and more.
platform: aspnet
control: Sparkline
documentation: ug
---

# Sparkline Dimensions in ASP.NET WebForms Sparkline

You can set the size directly on the Sparkline or to the container of the sparkline. When you do not specify the size, it takes 30px as the height and 50px as its width, by default.

## Set size for the container

You can customize the Sparkline dimension by setting the width and height for the container element.

{% highlight html %}

<body>

    <div id="container" style="width:820px;height:500px;">
        <ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server">           
        </ej:Sparkline>
    </div>

</body>

{% endhighlight %} 

![ASP.NET WebForms Sparkline dimension](Sparkline-Dimensions_images/Sparkline-Dimensions_img1.png)

## Set size in pixels 

You can also set the `Height` and `Width` for Sparkline by using the `Size` property of the Sparkline.

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" runat="server"> 
    <Size Height="40" Width="60"></Size>          
</ej:Sparkline>

{% endhighlight %}

## Responsive Sparkline

To resize the Sparkline when the browser or the sparkline container is resized, set the `IsResponsive` property to **true**, where the sparkline adapts to the changes in size of the container. 

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" IsResponsive="true" runat="server">    
</ej:Sparkline>

{% endhighlight %} 
