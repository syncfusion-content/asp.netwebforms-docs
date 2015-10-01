---
layout: post
title: Measure Groups | OLAPClient | ASP.NET Webforms | Syncfusion
description: measure groups 
platform: aspnet
control: OLAP Client
documentation: ug
---

# Measure Groups 

In Cube Dimension Browser tree-view can be viewed in a filtered manner through the Measure Groups option. This feature allows you to view the list of measure groups and dimensions associated with the selected measure group from the cube.

{% highlight html %}

<ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" EnableMeasureGroups="true" ></ej:OlapClient>

{% endhighlight %}

On selecting a measure group from the drop-down list, the Cube Dimension Browser tree-view displays the related dimensions as follows.

![C:/Users/Narendhran Muthuvel/Desktop/Capture7.PNG](Measure-Groups_images/Measure-Groups_img1.png) 


![C:/Users/Narendhran Muthuvel/Desktop/Capture44.PNG](Measure-Groups_images/Measure-Groups_img2.png) 