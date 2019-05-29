---
layout: post
title: Measure Groups | PivotClient | ASP.NET | Syncfusion
description: This document illustrates that how to define measure groups and functionalities in ASP.NET PivotClient control
platform: aspnet
control: PivotClient
documentation: ug
---

# Measure groups

I> This feature is applicable only for the OLAP data source bound from the server-side.

In Cube Dimension Browser, the tree view can be viewed in a filtered manner through the measure groups option. This feature allows you to view the list of measures and dimensions associated with the selected measure group from the cube. For enabling this, the `EnableMeasureGroups` property is set to true. By default, its value is set to false.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" Url="/OlapClient" Title="OLAP Browser" runat="server" EnableMeasureGroups="true"></ej:PivotClient>

{% endhighlight %}

By selecting a measure group from the drop-down list, the Cube Dimension Browser tree view displays the related measures and dimensions as follows:

![Measure group in ASP NET pivot client control](Measure-Groups_images/measuregroup.png)

![Internet sales Measure Group in ASP NET pivot client control](Measure-Groups_images/measuregroup1.png)
