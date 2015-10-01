---
layout: post
title: LiveTile Configuration | Tile | ASP.NET | Syncfusion
description: livetile configuration
platform: aspnet
control: Tile
documentation: ug
---

# LiveTile Configuration

Live Tiles are used to display the current or up to date information like scores, stocks, weather, etc. You can enable Live Tile using “data-ej-livetile-enabled” attribute by setting it to true. The “data-ej-livetile-type” attribute allows you to specify the type of animation while updating the information in Tile. There are three types of Tile animation supported: Flip, Slide and Carousel.

The“data-ej-livetile-imageurl” attribute sets background image for Live Tile. This property accepts array values so you can specify the image url’s for all the Tiles that are used in single Live Tile. 

You can specify time interval for each Tile update/animation using “data-ej-livetile-updateinterval” attribute. Time interval is given in milliseconds. The default value is 2000.

Refer to the following code examples.

{% highlight html %}

<div id="tile"></div>

<script>

	$("#tile").ejTile({

		tileSize: "medium", imagePosition: "fill",

		liveTile: {

			updateInterval: 2500, type: "flip", enabled: true,

			imageUrl: ['http://js.syncfusion.com/UG/Web/Content/tile/people_1.png', 'http://js.syncfusion.com/UG/Web/Content/tile/people_2.png']

		},

		text: "Peoples"

	})

</script>

{% endhighlight %}



In “data-ej-livetile-imagetemplateid” attribute, you can give Live Tile images outside the Tile rendering. To achieve this, you are required to give image content inside the element where the path is specified by templateid. You can update the “imageTemplateId” dynamically through updateTemplateID public method.

Refer to the following code examples. 



{% highlight html %}

<div id="tile"></div>

	<div id="temp1" style="background-image:

			url('http://js.syncfusion.com/UG/Web/Content/tile/people_1.png'); width: 100%; height: 100%;">

</div>

<div id="temp2" style="background-image:

		url('http://js.syncfusion.com/UG/Web/Content/tile/people_2.png'); width: 100%; height: 100%;">

</div>

<script>

	$("#tile").ejTile({

		tileSize: "medium", imagePosition: "fill",

		liveTile: {

			updateInterval: 2500, type: "flip", enabled: true,

			imageTemplateId: ["temp1", "temp2"]

		},

		text: "Peoples"

	})

</script> 

{% endhighlight %}



You can specify the array of images for Live Tile through CSS classes by using “data-ej-livetile-imageclass” attribute and you can define the desired styles in the specified class.

Refer to the following code examples.



{% highlight html %}

<div id="tile"></div>

<style>

	.people1 {

		background-image: url('http://js.syncfusion.com/UG/Web/Content/tile/people_1.png');

		width: 100%;

		height: 100%;

	}

	.people2 {

		background-image: url('http://js.syncfusion.com/UG/Web/Content/tile/people_2.png');

		width: 100%;

		height: 100%;

	}

</style>

<script>

	$("#tile").ejTile({

		tileSize: "medium", imagePosition: "fill",

		liveTile: {

			updateInterval: 2500, type: "flip", enabled: true,

			imageClass: ["people1", "people2"]

		},

		text: "Peoples"

	})

</script> 

{% endhighlight %}



