---
layout: post
title: RTL
description: rtl
platform: aspnet
control: DropDownList
documentation: ug
---

# RTL

This feature supports to change the left-to-right alignment of the DropDown widget to right-to-left (RTL). 

## Defining the RTL property

The following step explains the configuration of EnableRTL property in the DropDownList. 

{% highlight html %}

<div class="control">

    <ej:DropDownList ID="dropdownlist" TargetID="list" Width="200px" EnableRTL="true"

        runat="server">

    </ej:DropDownList>

    <div id="list">

        <ul>

            <li>Art</li>

            <li>Architecture</li>

            <li>Biography</li>

            <li>Comics</li>

            <li>Sports</li>

            <li>Science</li>

        </ul>

    </div>

</div>







{% endhighlight %}



Output of the above step.


![](RTL_images/RTL_img1.png)
{:.image }


