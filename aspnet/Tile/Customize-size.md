---
layout: post
title: Customize-size
description: customize size
platform: aspnet
control: Tile
documentation: ug
---

# Customize size

You can customize the size of the Tile by using the “data-ej-tileSize” attribute. The following built-in tile sizes are supported.

1. medium
2. small
3. large
4. wide

The default TileSize value is set to small.

Refer to the following code examples.

{% highlight html %}



    <div id="tile"></div>

    <script>

        $("#tile").ejTile({

            tileSize: "medium", imagePosition: "center",

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/pictures.png",

            text: "Pictures"

        })

    </script>	



{% endhighlight %}



 ![](Customize-size_images/Customize-size_img1.png) 
{:.image }


