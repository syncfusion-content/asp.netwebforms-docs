---
layout: post
title: Behavior Settings | Slider | ASP.NET | Syncfusion
description: Slider behavior settings for Webforms 
platform: aspnet
control: Slider
documentation: ug
---

# Behavior Settings 

## Height

By default, Slider renders a height of 14px. You can change the Slider height by using the Height property. Specify the value for this property in a string format.

## Width

By default, Slider control renders 100% width. You can customize the width of the Slider by using the Width property. Specify the value for this property in a string format.

The following steps explain you how to configure the height and width of the Slider.

In an ASPX page, define the Slider control and configure the Height and Width properties as required.

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Height="20" Width="500"> </ej:Slider>

{% endhighlight %}

The following screenshot displays the output of the above code example.

![Slider Width](Behavior-Settings_images/Behavior-Settings_img1.png)


## IncrementStep

This property sets the incremental step value for the Slider. When the Slider handle slides through mouse or keyboard, it increments / decrements the value based on the step value. By default, when the Slider handle is moved, single value increments / decrements. By using the IncrementStep property, you can change the increment step value. Data type of this property is number.

The following steps explain you how to configure the IncrementStep property.

In an ASPX page, define the Slider control and configure the IncrementStep property as required.

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Height="20" Width="500" IncrementStep="5"></ej:Slider>

{% endhighlight %}

The following screenshot displays the output of the above code example.

![IncrementStep](Behavior-Settings_images/Behavior-Settings_img2.png)



## ReadOnly

This feature prevents you from interacting with the Slider. That is, you can only view the Slider value and cannot change it.

The following steps explain you how to enable the ReadOnly property.

In an ASPX page, define the Slider control and set the ReadOnly property to true. 

{% highlight html %}

<ej:Slider ID="BasicSlider" runat="server" Height="20" Width="500" ReadOnly="true"></ej:Slider>

{% endhighlight %}