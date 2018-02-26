---
layout: post
title: External Search in Grid | Grid | ASP.NET Webforms | Syncfusion
description:  external search in grid
platform: aspnet
control: Grid
documentation: ug
---


# External Search in Grid

Using `search` method of grid, you can search the string in grid externally without using in-built toolbar search support. While using `search` method it is necessary to set `AllowSearching` property as `true`. The following code example explains the above behavior.
{% tabs %}
{% highlight html %}
<div class="content-container-fluid">
<div class="row">
<div id="Div1">
<div class="prop-grid">
<div class="row">
<div class="col-md-3">
<input type="text" id="inputText" class="e-ejinputtext" />
<ej:Button ID="search" runat="server" ClientSideOnClick="onSearching" Text="Searching"></ej:Button>
</div>
</div>
</div>
</div>    
<div class="cols-sample-area">
<ej:Grid ID="Grid" runat="server" AllowPaging="True" AllowSearching="True">
<Columns>
<ej:Column Field="OrderID" />
<ej:Column Field="CustomerID" />
<ej:Column Field="EmployeeID" />
<ej:Column Field="Freight" />
<ej:Column Field="ShipCity" />
<ej:Column Field="ShipCountry" />
</Columns>
</ej:Grid>
</div>

</div>
</div>

{% endhighlight %}

{% highlight js %}
function onSearching(args) {
var obj = $("#Grid").ejGrid("instance");
var val = $("#inputText").val();
obj.search(val);
}

{% endhighlight %}

{% endtabs %}
The following output is displayed as a result of the above code example.
![](ExternalSearch_images/Externalsearch_img1.jpeg)

