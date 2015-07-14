---
layout: post
title: Animation-with-DropDown-list
description: animation with dropdown list 
platform: aspnet
control: DropDownList
documentation: ug
---

## Animation with DropDown list 

This feature adds some animation effect to DropDown widget to show /hide the popup list. This is achieved by setting the Boolean value to the EnableAnimationproperty.

### Defining the Animation property

The following step explains the configuration of the EnableAnimationproperty in the DropDownList.

In an ASPX page, add an element to configure the DropDownList.

{% highlight html %}

<div class="control">

    <ej:DropDownList ID="dropdownlist" Width="200px" TargetID="list" EnableAnimation="true"

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



