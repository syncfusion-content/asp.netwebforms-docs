---
layout: post
title: TargetId
description: targetid
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# TargetId

This property is used to define the target Id for Navigation Drawer. The drawer opens while you click on the specified target element.

{% highlight html %}

<button id="drawerTarget" style="top:200px;left:600px;position:absolute"></button>



<div id="navpane">

        <ul>

            <li>Settings</li>

            <li>Read</li>

            <li>Help</li>

            <li>About</li>

        </ul>

</div>

<script>      

        $("#navpane").ejNavigationDrawer({ position: "fixed", targetId: "drawerTarget", enableListView: true, listViewSettings: { width: 300 }});

        $("#drawerTarget").ejButton({text:"Open Drawer"});

    </script>





{% endhighlight %}





The following screenshots illustrates the output.

![](TargetId_images/TargetId_img1.png) 
{:.image }




![](TargetId_images/TargetId_img2.png) 
{:.image }


