---
layout: post
title: Filtering | ListView | ASP.NET Webforms | Syncfusion
description: filtering
platform: aspnet
control: ListView
documentation: ug
---

# Filtering

**Filtering** is one of the key features of **ListView** control. The **Filtering** option is added into the **ListView** control when the `EnableFiltering` property is set to **“true”**. This enables a simple interface to filter items from a large collection of **ListView** items.

Refer the following code examples.


{% highlight html %}


    <ej:ListView ID="ListView1" runat="server" Height="450" Width="400" EnableFiltering="true" >
        <Items>
            <ej:ListViewItems Text="Artwork"></ej:ListViewItems>
            <ej:ListViewItems Text="Abstract"></ej:ListViewItems>
            <ej:ListViewItems Text="2 Acrylic Mediums"></ej:ListViewItems>
            <ej:ListViewItems Text="Creative Acrylic"></ej:ListViewItems>
            <ej:ListViewItems Text="Modern Painting"></ej:ListViewItems>
            <ej:ListViewItems Text="Canvas Art"></ej:ListViewItems>
            <ej:ListViewItems Text="Black white"></ej:ListViewItems>
            <ej:ListViewItems Text="Children"></ej:ListViewItems>
            <ej:ListViewItems Text="Preschool Crafts"></ej:ListViewItems>
            <ej:ListViewItems Text="School-age Crafts"></ej:ListViewItems>
        </Items> 
  </ej:ListView>

    
{% endhighlight %}


**Screenshot:**

![](Filtering_images/Filtering_img1.png)

Before Filtering
{:.caption}



![](Filtering_images/Filtering_img2.png)

After Filtering
{:.caption}

