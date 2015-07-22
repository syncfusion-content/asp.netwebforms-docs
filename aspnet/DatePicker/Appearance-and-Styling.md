---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: aspnet
control: DatePicker
documentation: ug
---

# Appearance and Styling

## Theme

DatePicker control’s style and appearance are controlled based on CSS classes. In order to apply Theme to the DatePicker control, you can refer to 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.widgets.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these both. 

By default, there are 13 themes support available for the DatePicker control namely,

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme
## Custom CSS


To apply custom styles to your DatePicker control, you can specify the CssClass property. The specified CSS name is added in the root of the DatePicker control.

In the ASPX page, include the following DatePicker control code example to enable the customized style.



{% highlight html %}

<ej:DatePicker ID="datepicker" runat="server" CssClass="custom"></ej:DatePicker>



{% endhighlight %}



Add the following styles to render the DatePicker with customized style. In the following CSS style, exiting theme style overrides by using root class custom.

{% highlight css %}

    .custom .e-header {

      background-color:blue;

    }
{% endhighlight %}




The following screenshot displays the output for the above code.



![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



