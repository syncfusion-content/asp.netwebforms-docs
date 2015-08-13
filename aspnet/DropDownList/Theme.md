---
layout: post
title: Theme
description: theme
platform: aspnet
control: DropDownList
documentation: ug
---

# Theme

DropDownList control’s style and appearance can be controlled based on CSS classes. In order to apply styles to the DropDownList control, you need to refer to two files namely, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.widgets.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two.

By default, there are 13 themes support available for DropDownList control namely,

•bootstrap-theme

•default-theme

•flat-azure-dark

•fat-lime

•flat-lime-dark

•flat-saffron

•flat-saffron-dark

•gradient-azure

•gradient-azure-dark

•gradient-lime

•gradient-lime-dark

•gradient-saffron

•gradient-saffron-dark

## Custom class with DropDown

CSS class can be used to customize the DropDown control appearance. Define a CSS class as per your requirement and assign the class name to the CssClass property. The data type of CssClass property is string.

Configuring the Custom CSS property

The following steps explain the configuration of CssClass properties in the DropDownList

In an ASPX page, add an element to configure the DropDownList

{% highlight javascript %}

<div class="control">
    <ej:DropDownList ID="dropdownlist" TargetID="list" Width="200px" CssClass="customclass"
        runat="server">
    </ej:DropDownList>
    <div id="list">
        <ul>
            <li>Art</li>
            <li>Architecture</li>
            <li>Biography</li>
            <li>Comics</li>
            <li>Sports</li>
            <li>Science</li>
        </ul>
    </div>
</div>

 {%endhighlight%}

 
Configure the CSS styles to apply on the DropDownList.


{% highlight css %}

  <style type="text/css">

        .customclass {

            background-color: #FFFFCC;

            font-weight: bold;

            font-family: sans-serif;

        }

    </style>
	
 {% endhighlight %}
 
 Output of the above steps.
 
 ![](Theme_images/Theme_img1.png)