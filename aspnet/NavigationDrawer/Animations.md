---
layout: post
title: Animations
description: animations
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Animations

You can set the transition type of the Navigation Drawer by using type property. The possible transition types are slide and overlay.

* Slide - both navigation panel and content page slides towards left/right direction to view the navigation panel items.
* Overlay - Only the navigation panel slides over the content page to view the navigation panel items. That is, part of the content page is hidden under navigation panel.

_Note:_ _Transition slide type works only with fixed position._

The default value is Overlay.

{% highlight html %}

    <div id="main" style="height:1000px;">

        <div id="navpane">

            <ul>

                <li>Settings</li>

                <li>Read</li>

                <li>Help</li>

                <li>About</li>

            </ul>

        </div>

        <button id="drawerTarget" style="top:200px;left:600px;position:absolute"></button>

    </div>

    <script>

        $("#navpane").ejNavigationDrawer({ type: "slide", position: "fixed", targetId: "drawerTarget", enableListView: true, listViewSettings: { width: 300 }});

        $("#drawerTarget").ejButton({ text: "OpenDrawer" });

    </script>



{% endhighlight %}





The following screenshot illustrates the output.

![](Animations_images/Animations_img2.png) 



![](Animations_images/Animations_img3.png) 



