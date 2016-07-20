---
layout: post
title: Add Group Tiles | Tile | ASP.NET | Syncfusion
description: add group tiles
platform: aspnet
control: Tile
documentation: ug
---

# Add Group Tiles

To make a Tile as grouped tile, you can use the following mentioned pre-defined classes.

<table>
<tr>
<th>
Class Name</th><th>
Explanation</th></tr>
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

  <div class="e-tile-group">
        <div class="e-tile-column">
            <ej:Tile ID="tile1" runat="server" ImagePosition="center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/alerts.png" Text="Alerts"></ej:Tile>
            <ej:Tile ID="tile2" runat="server" ImagePosition="Center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/pictures.png" Text="Pictures"></ej:Tile>            
            <ej:Tile ID="tile6" runat="server" ImagePosition="Center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/camera.png" Text="Camera"></ej:Tile>
            <ej:Tile ID="tile7" runat="server" ImagePosition="center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/messages.png" Text="Messages"></ej:Tile>
            <ej:Tile ID="tile8" runat="server" ImagePosition="center" TileSize="Wide" ImageUrl="../Content/themes/images/tile/windows/games.png" Text="Games"></ej:Tile>
        </div>
        <div class="e-tile-column">
            <ej:Tile ID="tile9" runat="server" ImagePosition="center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/map.png" Text="Map"></ej:Tile>
            <ej:Tile ID="tile10" runat="server" ImagePosition="Center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/bing.png" Text="Bing"></ej:Tile>
            <ej:Tile ID="tile11" runat="server" ImagePosition="Center" TileSize="medium" ImageUrl="../Content/themes/images/tile/windows/health.png" Text="Health"></ej:Tile>
            <ej:Tile ID="tile3" runat="server" ImagePosition="fill" TileSize="medium" ImageUrl="../Content/themes/images/tile/windows/people_1.png" Text="Peoples"></ej:Tile>
            <ej:Tile ID="tile12" runat="server" ImagePosition="Center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/weather.png" Text="weather"></ej:Tile>
            <ej:Tile ID="tile13" runat="server" ImagePosition="Center" TileSize="Medium" ImageUrl="../Content/themes/images/tile/windows/music.png" Text="Music"></ej:Tile>
        </div>
    </div>

{% endhighlight %}



![](Add-Group-Tiles_images/Add-Group-Tiles_img1.png) 


Tile - Group Tiles
{:.caption}
