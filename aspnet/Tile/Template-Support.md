---
layout: post
title: Template-Support
description: template support
platform: aspnet
control: Tile
documentation: ug
---

# Template Support

The“data-ej-imagetemplateid” attribute is used to customize the image of Tile with template feature by setting the id. The“data-ej-captiontemplateid” attribute is used to customize the text of Tile with template feature by setting the id. 

Refer to the following code examples.

{% highlight html %}



    <div id="tile"></div>

    <div id="imageTemplate">

        <div id="appimage">

        </div>

        <div class="tileMargin">

            <span class="caption">Google Search</span><br />

            <span class="description">The world’s information</span><br />

            <span class="sub">Free</span>

        </div>

    </div>

    <div id="captionTemplate" class="title">Windows Store</div>

    <script>

        $("#tile").ejTile({ tileSize: "wide", imageTemplateId: "imageTemplate", captionTemplateId: "captionTemplate" })

    </script>




{% endhighlight %}



Add the following code example.

{% highlight html %}

    <style>

        #appimage {

            background-image: url("http://js.syncfusion.com/UG/mobile/content/google.png");

            background-position: center center;

            background-repeat: no-repeat;

            background-size: 50% auto;

            display: table-cell;

            width: 45%;

        }

        .tileMargin {

            display: table-cell;

            padding-top: 25px;

        }

        .e-tile-template {

            display: table;

            height: 100%;

            width: 100%;

        }

    </style>





{% endhighlight %}



![](Template-Support_images/Template-Support_img1.png) 
{:.image }


