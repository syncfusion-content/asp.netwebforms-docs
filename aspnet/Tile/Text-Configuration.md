---
layout: post
title: Text Configuration | Tile | ASP.NET | Syncfusion
description: text configuration
platform: aspnet
control: Tile
documentation: ug
---

# Text Configuration

The “caption-text” attribute is used to set the caption of a Tile as a Text on initialization. The “caption-alignment” attribute is used to align the Tile text as normal on initialization. Before that we need to set true to the “caption-enabled” property. The possible position values for “caption-alignment” are as follows: 

1. normal 
2. left
3. right
4. center



Refer to the following code examples.

{% highlight html %}


      <ej:Tile runat="server" ImagePosition="Center" ImageUrl="../Content/images/tile/camera.png" TileSize="Medium" >
             <CaptionTile Enabled="true" Text="Camera" Alignment="Center" />
      </ej:Tile>    


{% endhighlight %}



![](Text-Configuration_images/Text-Configuration_img1.png) 



