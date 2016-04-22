---
layout: post
title: Hiding-Summary
description: hiding summary
platform: aspnet
control: OlapClient
documentation: ug
---

# Hiding Summary

By setting the “GridLayout” property as “NoSummaries”, the summary cells in PivotGrid control is hidden. By default, “Normal” layout is set.

{% highlight html %}

<ej:OlapClient Url="../OlapClient" Title="OLAP Browser" runat="server" GridLayout="NoSummaries"></ej:OlapClient>
    
{% endhighlight %}

