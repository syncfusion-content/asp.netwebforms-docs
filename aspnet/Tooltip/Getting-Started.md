---
layout: post
title: Getting Started | Tooltip | ASP.NET | Syncfusion
description: How to create the Tooltip
platform: aspnet
control: Tooltip
documentation: ug
keywords : ASP Tooltip, Tooltip, asp Tooltip, ASP Tooltip widget, ASP Tooltip Appearance, ASP Tooltip Dimensions
---
# Getting started

## Create a Tooltip

Using the following steps, you can create a Tooltip control. The basic rendering of ASP.NET Tooltip is achieved with default functionality.



1. You can create an ASP.NET Project and add necessary assembly and script with the help of the given [WebForms-Getting Started](http://help.syncfusion.com/aspnet/getting-started) Documentation.



2. Add the mentioned code to the corresponding ASPX page for Tooltip rendering.

{% highlight html %}

    <div class="frame">    
        <div class="img" id="sample">
            <a target="_blank" href="image/taj.png">
            <img src="http://asp.syncfusion.com/demos/web/content/images/tooltip/template-05.png" alt="Delphi">
            </a>
            <div class="desc">Delphi Succinctly</div>
        </div>
    </div>

    <ej:Tooltip For="sample" runat="server" ClientIDMode="Static"  Content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms."></ej:Tooltip>
    
{% endhighlight %}

Apply the following style sheet

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            width: 159px;
            height: 213px;
            left: 35%;
            position: relative;
            top: 20%;
        }
        div.img img {
            width: 159px;
            height: 179px;
        }
        div.desc {
            padding: 8px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![](Getteing-Started_images/Getteing-Started_img1.jpeg)

## Setting Dimensions

Tooltip dimensions can be set using [width](http://help.syncfusion.com/js/api/ejtooltip#members:width) and [height](http://help.syncfusion.com/js/api/ejtooltip#members:height) API.

{% highlight html %}
 
    <div class="control">
        TypeScript lets you write <a id="testSample"><u> JavaScript</u> </a>the way you really want to.
    </div>

    <ej:Tooltip For="testSample" runat="server" ClientIDMode="Static"  Content="JavaScript is the programming language of HTML and the Web." Width="100px" Height="100px"></ej:Tooltip>
    
{% endhighlight %}

## Tooltip Appearance 

You can configure the appearance of the Tooltip with the title, close button and call out as your application requires.

{% highlight html %}
 
    <div class="img" id="sample2">
        <a target="_blank" href="image/taj.png">
        <img src="http://asp.syncfusion.com/demos/web/content/images/tooltip/template-05.png" alt="Delphi">
        </a>
        <div class="desc">Delphi Succinctly</div>
    </div>

    <ej:Tooltip For="sample2" runat="server" ClientIDMode="Static"  Content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms." Width="180px" Title="Delphi Succinctly" CloseMode="Sticky" IsBalloon="false"></ej:Tooltip>
    
{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            float: left;
            box-sizing: border-box;
            height: 200px;
            width: 146px;
        }
        div.img img{
            width: 100%;
            height: 166px;
        }
        div.desc {
            padding: 6px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![](Getteing-Started_images/Getteing-Started_img2.jpeg)

