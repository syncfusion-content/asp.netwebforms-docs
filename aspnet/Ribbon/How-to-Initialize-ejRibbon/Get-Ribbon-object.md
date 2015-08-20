---
layout: post
title: Get-Ribbon-object
description: get ribbon object
platform: aspnet
control: Ribbon
documentation: ug
---

## Get Ribbon object

After _Ribbon_ initialization, _Ribbon_ object is stored in a container element of _Ribbon_. To access _Ribbon_ object, you can use the following code example.

{% highlight js %}

var ribbonObject = $("#Ribbon").ejRibbon("instance");

[or]

var ribbonObject = $("#Ribbon").data("ejRibbon");

{% endhighlight %}







