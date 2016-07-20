---
layout: post
title: Template Support | Tile | ASP.NET | Syncfusion
description: template support
platform: aspnet
control: Tile
documentation: ug
---

# Template Support

The “imageTemplateId” attribute is used to customize the image of Tile with template feature by setting the id. 

Refer to the following code examples.

{% highlight html %}

     <ej:Tile runat="server"  ImageTemplateId="imageTemplate" TileSize="Wide" >  </ej:Tile>    
 
          <div id="imageTemplate">

            <div id="appimage">

            </div> 

            <div class="tileMargin">

                <span class="caption">Google Search</span><br />

                <span class="description">The world’s information</span><br />

                <span class="sub">Free</span>
            </div>    
        </div>
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

