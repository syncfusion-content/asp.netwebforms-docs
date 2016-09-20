---
layout: post
title: Behavior-Settings | RadialSlider | ASP.NET | Syncfusion
description: behavior-settings
platform: aspnet
control: RadialSlider
documentation: ug
---
# Behavior settings

The following are some  properties that enables you to an option to enhance the behavior of **RadialSlider** control.

##  Show/hide RadialSlider on initial rendering 

The **RadialSlider** property **AutoOpen** allow to enable or disable RadialSlider visibility. By default,Value of the property is set as **true** and type of the property is **Boolean**.

{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server" AutoOpen="false"></ej:RadialSlider>      
    
{% endhighlight %}

## Value accuracy  

The **RadialSlider** property **EnableRoundOff** allow  to show  the rounded off value when user changes it. By default, value of the property is set as **true**. For accurate values you can set this as false.

{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server" EnableRoundOff="false"></ej:RadialSlider>

{% endhighlight %}

## Display inline

The **RadialSlider** property **Inline** is used to show the control values inline of the slider. By default, value of the property is set as **false**.

{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server" Inline="true"></ej:RadialSlider>

{% endhighlight %}

## Modifying Label Space 

The **RadialSlider** property **LabelSpace** allow to define the space of label in it. By default, the **RadialSlider** labelSpace is set as 30. Refer to the following code example.

{% highlight html %}

    <ej:RadialSlider ID="slider" LableSpace=40 runat="server"></ej:RadialSlider>

{% endhighlight %}

The following screenshot shows the output for the above code example.

![](Behavior-settings_images\Behavior-settings_images_img1.png)


## Show/Hide inner circle

The **RadialSlider** property **ShowInnerCircle** allow to show  or hide  the inner circle of  the **RadialSlider**.By default,Value of the property is set as **true** and type of the property is **Boolean**.

{% highlight html %}

    <ej:RadialSlider ID="slider" ShowInnerCircle="false" InnerCircleImageUrl="../images/radialslider/chevron-right.png" runat="server"></ej:RadialSlider>  

{% endhighlight %}

The following screenshot shows the output for the above code example.

![](Behavior-settings_images\Behavior-settings_images_img2.png)

## Values customization

The **RadialSlider** property **Ticks** allow to set an array of numeric value which will be displayed in it. By Default **RadialSlider** ticks value is a set to an array of length 11 as following,

Ticks= new List<double>{ 0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 }. You can refer the below code for reference.

{% tabs %}
{% highlight html %}

    <ej:RadialSlider ID="slider" runat="server"></ej:RadialSlider>

{% endhighlight %}

{% highlight c# %}

    protected void Page_Load(object sender, EventArgs e)
    {
    this.slider.Ticks = new List<double> { 100, 200, 300, 400, 500, 600, 700, 800, 900, 1000 };
    }

{% endhighlight %}
{% endtabs %}

The following screenshot shows the output for the above code example.

![](Behavior-settings_images\Behavior-settings_images_img3.png)
