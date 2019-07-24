---
layout: post
title: selection | ListView | ASP.NET Webforms | Syncfusion
description: selection
platform: aspnet
control: ListView
documentation: ug
---

# Selection

**MultiSelection**

**ListView** has a checklist feature that is used to select multiple list items at the same time in the **ListView**. For this, set `EnableCheckMark` property to **“true”**.

Refer the following code examples.


{% highlight html %}

<ej:ListView ID="List" runat="server" EnableCheckMark="true">

    <Items>
        <ej:ListViewItems Text="Artwork"></ej:ListViewItems>
        <ej:ListViewItems Text="Abstract"></ej:ListViewItems>
        <ej:ListViewItems Text="2 Acrylic Mediums"></ej:ListViewItems>
        <ej:ListViewItems Text="Creative Acrylic"></ej:ListViewItems>
        <ej:ListViewItems Text="Modern Painting"></ej:ListViewItems>
        <ej:ListViewItems Text="Canvas Art"></ej:ListViewItems>
        <ej:ListViewItems Text="Black white"></ej:ListViewItems>
        <ej:ListViewItems Text="Children"></ej:ListViewItems>
    </Items>

</ej:ListView>

{% endhighlight %}

Run the codes to get the following output

![Selection](Selection_images/Selection_img1.png) 

**PreventSelection**

When selecting a specific list item, it is highlighted with an active color. `PreventSelection` property is used to prevent this behavior by setting it to **“true”**. 

N> When the click or select action is completed, the highlight is undone automatically even when the  property is set to “false”.

Refer the following code examples.



{% highlight html %}

<ej:ListView ID="ListView1" runat="server" Height="450" Width="400" PreventSelection="true">

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

**PersistSelection**

`PersistSelection` property is used to highlight the selected item in the **ListView** control even after touch end happens. By default, the active state is removed once the touch end happens.

Refer the following code examples.



{% highlight html %}
    <ej:ListView ID="ListView1" runat="server" Height="450" Width="400" PreventSelection="true">
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


Run the codes to get the following output

![Persistance](Selection_images/Selection_img2.png) 
