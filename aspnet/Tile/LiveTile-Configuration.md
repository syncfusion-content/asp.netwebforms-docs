---
layout: post
title: LiveTile Configuration | Tile | ASP.NET | Syncfusion
description: livetile configuration
platform: aspnet
control: Tile
documentation: ug
---

# LiveTile Configuration

Live Tiles are used to display the current or up to date information like scores, stocks, weather, etc. You can enable Live Tile using “liveTile-enabled” attribute by setting it to true. The “liveTile-type” attribute allows you to specify the type of animation while updating the information in Tile. There are three types of Tile animation supported: Flip, Slide and Carousel.

The “liveTile-imageUrl” attribute sets background image for Live Tile. This property accepts array values so you can specify the image url’s for all the Tiles that are used in single Live Tile. 

You can specify time interval for each Tile update/animation using “liveTile-updateInterval” attribute. Time interval is given in milliseconds. The default value is 2000.

Refer to the following code examples.

{% highlight html %}


     <ej:Tile runat="server" TileSize="Medium"> 

	   <LiveTile Enabled="true" ImageTemplateId=["temp1","temp2"] Type="Flip" UpdateInterval="3000" />
	   
	</ej:Tile>       
 
          <div id="temp1" style="background-image:url('http://js.syncfusion.com/UG/Web/Content/tile/people_1.png'); width: 100%; height: 100%;">

        </div>

        <div id="temp2" style="background-image:url('http://js.syncfusion.com/UG/Web/Content/tile/people_2.png'); width: 100%; height: 100%;">

        </div>

{% endhighlight %}



In “liveTile-imageTemplateId” attribute, you can give Live Tile images outside the Tile rendering. To achieve this, you are required to give image content inside the element where the path is specified by templateId. You can update the “imageTemplateId” dynamically through updateTemplateID public method.



You can specify the array of images for Live Tile through CSS classes by using “liveTile-imageClass” attribute and you can define the desired styles in the specified class.

Refer to the following code examples.



{% highlight html %}



 <ej:Tile runat="server" ImagePosition="Center" TileSize="Medium"> 

	   <LiveTile Enabled="true" ImageClass=["people1","people2"] Type="Flip" UpdateInterval="3000" />

	</ej:Tile> 



<style>

	.people1 {

		background-image: url('../Content/tile/people_1.png');

		width: 100%;

		height: 100%;

	}

	.people2 {

		background-image: url('../Content/tile/people_2.png');

		width: 100%;

		height: 100%;

	}

</style> 

{% endhighlight %}



