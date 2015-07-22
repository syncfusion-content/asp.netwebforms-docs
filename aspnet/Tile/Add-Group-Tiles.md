---
layout: post
title: Add-Group-Tiles
description: add group tiles
platform: aspnet
control: Tile
documentation: ug
---

# Add Group Tiles

To make a Tile as grouped tile, you can use the following mentioned pre-defined classes.

<table>
<tr>
<td>
Class Name</td><td>
Explanation</td></tr>
<tr>
<td>
group</td><td>
To group the column elements</td></tr>
<tr>
<td>
column</td><td>
To align the tile in column manner</td></tr>
<tr>
<td>
small-col-2</td><td>
To align the small size tiles</td></tr>
</table>


To render group tile, refer to the following code example.

{% highlight html %}



<div class="group">

    <div class="column">

           <!— Add tile control here -->

    </div>

</div>





{% endhighlight %}



To render column grouped tile, you need to render the number of tiles inside a &lt;div&gt; element with class ‘column’. Then that column group element is appended to a &lt;div&gt; with class ‘group’.     

To render small-col-2 grouped tile, you need to render the number of tiles inside a &lt;div&gt; element with class ‘small-col-2’. Then that small-col-2 group element is appended to a &lt;div&gt; with class ‘column’. Then you need to append those column inside the main group &lt;div&gt; element.                                                     

 Refer to the following code examples.

{% highlight html %}



<div class="group">

        <div class="column">

            <div id="tile1">

            </div>

            <div id="tile2">

            </div>

            <div id="tile3">

            </div>

            <div id="tile4">

            </div>

            <div id="tile5">

            </div>

        </div>

        <div class="column">

            <div id="tile6">

            </div>

            <div id="tile7">

            </div>

            <div id="tile8">

            </div>

            <div id="tile9">

            </div>

            <div id="tile10">

            </div>

            <div id="tile11">

            </div>

        </div>

    </div>



    <script>

        $("#tile1").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/alerts.png",

            text: "Alerts"

        });

        $("#tile2").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/pictures.png",

            text: "Pictures"

        });

        $("#tile3").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/camera.png",

            text: "Camera"

        });

        $("#tile4").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/messages.png",

            text: "Messages"

        });

        $("#tile5").ejTile({

            tileSize: "wide", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/games.png",

            text: "Games"

        });

        $("#tile6").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/map.png",

            text: "Map"

        });

        $("#tile7").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/bing.png",

            text: "Bing"

        });

        $("#tile8").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/favs.png",

            text: "Health"

        });

        $("#tile9").ejTile({

            tileSize: "medium", imagePosition: "fill",

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/people_2.png",

            text: "Peoples"

        });

        $("#tile10").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/weather.png",

            text: "Weather"

        });

        $("#tile11").ejTile({

            tileSize: "medium", 

            imageUrl: "http://js.syncfusion.com/UG/Web/Content/tile/music.png",

            text: "Music"

        });

    </script>





{% endhighlight %}



![](Add-Group-Tiles_images/Add-Group-Tiles_img1.png) 
{:.image }


_Tile - Group Tiles_

