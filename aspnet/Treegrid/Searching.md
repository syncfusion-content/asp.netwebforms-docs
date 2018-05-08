---
layout: post
title: Searching | TreeGrid | ASP.NET | Syncfusion
description: Searching
platform: aspnet
control: TreeGrid
documentation: ug
---

## Searching

The TreeGrid control has an option to search its content using toolbar search box. The toolbar search box can be enabled by using the `ToolbarSettings.ToolbarItems` property. The following code example explains how to integrate search textbox in toolbar.

{% highlight html %}

    <ej:TreeGrid ID="TreeGrid" runat="server">
        <ToolbarSettings ShowToolbar="true" ToolbarItems="search" />            
    </ej:TreeGrid>

{% endhighlight %}

The below screenshot shows TreeGrid search with `plan` key word.
![](Searching_images/Searching_img1.png)
