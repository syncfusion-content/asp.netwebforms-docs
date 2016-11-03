---
layout: post
title: Appearance and Styling | ToggleButton | ASP.NET | Syncfusion
description: appearance and styling
platform: aspnet
control: ToggleButton
documentation: ug
---

# Appearance and Styling

## Theme support

You can control the style and appearance of the Toggle Button based on the CSS classes. To apply styles to the Toggle Button control, you can refer to the files, ej.widgets.core.min.css and ej.theme.min.css. When you refer to ej.widgets.all.min.css file, it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two files                 . 

By default, there are 13 themes available for Toggle Button control namely,

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


You can use the CSS to customize the appearance of the Toggle Button control. Define a CSS class as per the requirement and assign the class name to the CssClass property.

The following steps explains the rendering of the Toggle Button with custom CSS.

In the ASPX page, add the following button elements to configure Toggle Button.

{% highlight html %}

<table>

    <tr>

        <td>

            <ej:ToggleButton ID="ToggleButton_CustomCss1" runat="server" Size="Small" ShowRoundedCorner="true" ContentType="TextAndImage" DefaultText="Play" ActiveText="Next" DefaultPrefixIcon="e-icon e-mediaplay"                ActivePrefixIcon="e-icon e-mediapause" CssClass="customCss1">

            </ej:ToggleButton>

        </td>

        <td>

            <ej:ToggleButton ID="ToggleButton_CustomCss2" runat="server" Size="Small" ShowRoundedCorner="true" ContentType="TextAndImage" DefaultText="Play" ActiveText="Next" DefaultPrefixIcon="e-icon e-mediaplay"                ActivePrefixIcon="e-icon e-mediapause" CssClass="customCss2">

            </ej:ToggleButton>

        </td>

        <td>

            <ej:ToggleButton ID="ToggleButton_CustomCss3" runat="server" Size="Small" ShowRoundedCorner="true" ContentType="TextAndImage" DefaultText="Play" ActiveText="Next" DefaultPrefixIcon="e-icon e-mediaplay"                ActivePrefixIcon="e-icon e-mediapause" CssClass="customCss3">

            </ej:ToggleButton>

        </td>

        <td>

            <ej:ToggleButton ID="ToggleButton_CustomCss4" runat="server" Size="Small" ShowRoundedCorner="true" ContentType="TextAndImage" DefaultText="Play" ActiveText="Next" DefaultPrefixIcon="e-icon e-mediaplay"                ActivePrefixIcon="e-icon e-mediapause" CssClass="customCss4">

            </ej:ToggleButton>

        </td>

        <td>

            <ej:ToggleButton ID="ToggleButton_CustomCss5" runat="server" Size="Small" ShowRoundedCorner="true" ContentType="TextAndImage" DefaultText="Play" ActiveText="Next" DefaultPrefixIcon="e-icon e-mediaplay"                ActivePrefixIcon="e-icon e-mediapause" CssClass="customCss5">

            </ej:ToggleButton>

        </td>

    </tr>

</table>

{% endhighlight %}

Configure the CSS styles to apply on buttons.



{% highlight css %}

.e-togglebutton.customCss1

{

	background-color: #121111;

}

.e-togglebutton.customCss2

{

	background-color: #94bbd5;

}

.e-togglebutton.customCss3

{

	background-color: #f3533c;

}

.e-togglebutton.customCss4

{

	background-color: #d1eeed;

}

.e-togglebutton.customCss5

{

	background-color: #deb66e;

}

/* Customize the button image & text color */

.e-togglebutton.customCss1.e-btn.e-select .e-icon, .e-togglebutton.customCss1.e-btn.e-select .e-btntxt

{

	color: #94bbd5;

}

.e-togglebutton.customCss2.e-btn.e-select .e-icon, .e-togglebutton.customCss2.e-btn.e-select .e-btntxt

{

	color: #121111;

}

.e-togglebutton.customCss3.e-btn.e-select .e-icon, .e-togglebutton.customCss3.e-btn.e-select .e-btntxt

{

	color: #cef6f7;

}

.e-togglebutton.customCss5.e-btn.e-select .e-icon, .e-togglebutton.customCss5.e-btn.e-select .e-btntxt

{

	color: #534f4f;

}

{% endhighlight %}



Run the above code to render the following output.

 ![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 



