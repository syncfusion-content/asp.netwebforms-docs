---
layout: post
title: Measure Groups | PivotClient | ASP.NET | Syncfusion
description: measure groups 
platform: aspnet
control: PivotClient
documentation: ug
---

# Measure Groups 

I> This feature is applicable only for OLAP data source bound from server-side.

In Cube Dimension Browser, treeview can be viewed in a filtered manner through the Measure Groups option. This feature allows you to view the list of measures and dimensions associated with the selected measure group from the cube. For enabling this, the `EnableMeasureGroups` property is set to true. By default, its value is set to false.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" Url="/OlapClient" Title="OLAP Browser" runat="server" EnableMeasureGroups="true"></ej:PivotClient>

{% endhighlight %}

On selecting a measure group from the drop-down list, the Cube Dimension Browser treeview displays the related measures and dimensions as follows.

![](Measure-Groups_images/measuregroup.png) 

![](Measure-Groups_images/measuregroup1.png)
