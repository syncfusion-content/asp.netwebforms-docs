---
layout: post
title: Levels | SunburstChart | ASP.NET Webforms | Syncfusion
description: Learn about levels support in Syncfusion ASP.NET Webforms SunburstChart control and more details.
platform: aspnet
control: SunburstChart
documentation: ug
---

## Levels

Sunburst chart is used to display hierarchical data. You can add more than one hierarchical data by using the **Levels** property of Sunburst chart. Each level of the hierarchy is represented by circle.
The following code snippet illustrates 

{% highlight html %}
<ej:SunburstChart  ID="container" runat="server" >
<Levels>
  <%--To Add Multiple levels for reprsenting the hierarchical data   --%>
</Levels>  
</ej:SunburstChart> 

{% endhighlight %}

## GroupMemberPath

It is the string property that is used to map the group category value in the dataSource .
You can define the levels as shown in the below code example

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server" >
<Levels>
                <ej:SunburstLevel GroupMemberPath="Level1"></ej:SunburstLevel>
                <ej:SunburstLevel GroupMemberPath="Level2"></ej:SunburstLevel>
                <ej:SunburstLevel GroupMemberPath="Level3"></ej:SunburstLevel>
              
            </Levels>  
</ej:SunburstChart> 
 {% endhighlight %}

The following screenshot illustrates the Sunburst Chart with different levels

![ASPNET SunburstChart Levels Image1](Levels_images/Levels_img1.png)
