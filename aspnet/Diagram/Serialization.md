---
layout: post
title: Serialization | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to process saving and loading for state persistence of the Diagram.
platform: aspnet
control: Diagram
documentation: ug
---

# Serialization

**Serialization** is the process of saving and loading for state persistence of the Diagram.

## Save

The Diagram is serialized as JSON data while saving. The client side method, `save` helps to serialize the Diagram as JSON. The following code illustrates how to save the Diagram.

{% highlight js %}

var diagram = $("#Diagram").ejDiagram("instance");

//save() returns serialized JSON data of the Diagram
var json = diagram.save();

{% endhighlight %}

This JSON data can be converted to string and stored for future use. The following snippet illustrates how to save the serialized JSON into local storage.

{% highlight js %}

//Saves the JSON object in to local storage
localStorage.setItem("diagram", JSON.stringify(json));

{% endhighlight %}

Diagram can also be saved as raster or vector image files. For more information about saving the Diagram as images, refer to [Exporting](/aspnet/Diagram/Exporting "Exporting").


## Load

Diagram is loaded from the Serialized JSON data. The client side method, `load` helps you to load the Diagram from the serialized JSON. The following code illustrates how to load the Diagram from serialized JSON data.

{% highlight js %}

//Retrieves the JSON object from local storage
json = JSON.parse(localStorage.getItem("diagram"));

//Loads the Diagram from saved JSON data
diagram.load(json);

{% endhighlight %}

N> Before loading a new Diagram, existing Diagram is cleared.

## Limitation

There are some limitations in saving/loading the Diagrams and they are listed as follows.

* When define the events as a string, functions need to be maintained in the application level while loading the diagram.

{% tabs %}
{% highlight aspx-cs %}

<ej:Diagram ID="DiagramContent" runat="server" Height="400px" Width="100%" OnClientNodeCollectionChange="nodeCollectionChange">
</ej:Diagram>

{% endhighlight %}

{% highlight js %}

function nodeCollectionChange(args) {
}

{% endhighlight %}
{% endtabs %}

* HTML / Native template needs to be retained in the application level, while loading the native and HTML node.

{% highlight aspx-cs %}

<!-- Template content needs to be retained while loading the diagram.-->
<script id="htmlTemplate" type="text/x-jsrender">
	<div>
		<input type="button" value="button" style="color: #ffffff; background-color: #fbb139; border-color: #f89b1c" />
	</div>
</script>

{% endhighlight %}

{% highlight js %}

diagram.load(json);

{% endhighlight %}

* CSS classes have to be retained in the application level, while loading the Diagram.

{% highlight aspx-cs %}

<style>
	<!-- CSS class needs to be retained while loading the Diagram.-->
	.nodeCss {
		fill: black;
		stroke: cyan;
	}
</style>

{% endhighlight %}

{% highlight js %}

diagram.load(json);

{% endhighlight %}