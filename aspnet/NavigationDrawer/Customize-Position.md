---
layout: post
title: Customize-Position
description: customize position
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Customize Position

Position property is used to specify the position whether it is in fixed or relative to the page. When you set a normal value to position property, it appears within the container. Otherwise, it appears in the whole body .The possible position values are fixed and normal. The Default value is normal.

{% highlight html %}

    <div id="main" style="height:700px;">

        <div id="navpane">

            <ul>

                <li>Settings</li>

                <li>Read</li>

                <li>Help</li>

                <li>About</li>

            </ul>

        </div>

    </div>

    <script>

        $("#navpane").ejNavigationDrawer({ position: "fixed", enableListView: true, listViewSettings: { width: 300 } });

    </script>



{% endhighlight %}





The following screenshot illustrates the output by swiping from left to right at the left end of the screen.

![](Customize-Position_images/Customize-Position_img1.png) 
{:.image }


