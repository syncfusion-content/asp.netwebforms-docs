---
layout: post
title: Appearance and Styling | WaitingPopup | ASP.NET | Syncfusion
description: appearance and styling 	
platform: aspnet
control: WaitingPopup
documentation: ug
---

# Appearance and Styling 	

## Custom Text

There is support for Custom Text to mention any message in the pop-up panel.  You can specify a custom text via the option Text that is displayed when the Waiting Popup is loading.

The following steps explain the configuration of the custom text for WaitingPopup control.

Add the following code example to the corresponding ASPX page to render the WaitingPopup control with customized custom text.

{% highlight html %}

<div id="targetelement"></div>

<ej:WaitingPopup ID="target" runat="server" Target="#targetelement" ShowOnInit="True" Text="Loading... Please wait..."></ej:WaitingPopup>

{% endhighlight %}



Add the following styles to render the WaitingPopup control

{% highlight css %}

<style type="text/css">

    #targetelement {

        height: 320px;

        width: 600px;

    }
	
	.e-waitpopup-pane .e-text {
	
		color: white;
		
	}
	
</style>

{% endhighlight %}

The following screenshot displays the output for the above code.

 ![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 



## Template

Provides support for the template to customize the appearance of the WaitingPopup such as including HTML content instead of the default image.

The following steps explain how to define a template to display the text and image for WaitingPopup control.

Add the following code example to the corresponding ASPX page to render the WaitingPopup control with customized template.

{% highlight html %}

<div id="targetelement"></div>

<ej:WaitingPopup ID="target" runat="server" Target="#targetelement" ShowOnInit="True" Template="#content" CssClass="waiting"></ej:WaitingPopup>

<div id="content">

    <div class="block">

        <div class="logo"></div>

        <div class="txt">

            <p>Create cutting-edge </p>

            <p><b>HTML5</b> web applications </p>

            <p>with ease </p>

        </div>

    </div>

    <div class="loader"></div>

</div>

{% endhighlight %}



In CSS, the custom styles need to be configured for the WaitingPopup.

N> Images for this sample are available at ‘installed location/Content/images’ and images are to be defined in the mentioned CSS. Then the images are displayed.

{% highlight css %}

<style type="text/css" class="cssStyles">

    #targetelement {

        height: 320px;

        margin: 0 auto;

        width: 600px;
    }

    .block {

        height: 76px;

    }



    .logo {

        background-image: url("../Content/images/waitingpopup/js_logo.png");

        float: left;

        height: 100%;

        width: 77px;

        margin-right: 15px;

    }



    .txt {

        float: left;

        font-size: 17px;

        height: 100%;

        text-align: left;
		
		color:white;
		
    }



        .txt p {

            margin: 0;

        }



    .loader {

        background: url("../Content/images/waitingpopup/load_light.gif") no-repeat scroll -5px 18px transparent;

        height: 40px;

        width: 100%;

    }



    .darktheme .loader {

        background-image: url("../Content/images/waitingpopup/load_dark.gif");

    }



    #content {

        cursor: default;

        height: 112px;

        width: 285px;

    }

</style>

{% endhighlight %}



Run the above code for the following output.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) 

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Web\samples\web\content\images\waitingpopup<br/>


## CSS Class

The CSS class can be used to customize the WaitingPopup control’s appearance. Define a CSS class as per the requirement and assign the class name to CssClass property.

The following steps allows you to configure CSS class for an auto-complete textbox.

Add the following code example to the corresponding ASPX page to render the WaitingPopup control on page load.

{% highlight html %}

<div id="targetelement"></div>

<ej:WaitingPopup ID="target" runat="server" Target="#targetelement" ShowOnInit="True" CssClass="custom" Text="Loading... Please wait..."></ej:WaitingPopup>

{% endhighlight %}



Define the CSS class for customizing the WaitingPopup control.

{% highlight css %}

<style type="text/css">

    #targetelement {

        height: 320px;

        width: 600px;

    }



    .custom {

        background-color: darkred;

        font-style: italic;

        font-weight: bolder;

        opacity: 0.5;
		
		color: white;

    }

</style>

{% endhighlight %}



The following screenshot displays the output for the above code.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png) 





