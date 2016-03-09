---
layout: post
title: Keyboard interaction | Rotator | ASP.NET Webforms | Syncfusion
description: keyboard interaction
platform: aspnet
control: Rotator
documentation: ug
---

# Keyboard interaction

The Rotator property, AllowKeyboardNavigation, turns on the keyboard interaction with the Rotator items. You must set this property to true to access the keyboard shortcuts. The default value is true. The value set to this property is Boolean.

The entire Rotator commands are accessed through the keyboard by specifying the KeyboardShortcut in the following table.

<table>
<tr>
<th>
KeyboardShortcut               </th><th>
Functions</th></tr>
<tr>
<td>
Alt + j</td><td>
Focuses the control</td></tr>
<tr>
<td>
UP</td><td>
Navigates up and left.</td></tr>
<tr>
<td>
Down</td><td>
Navigates down and right.</td></tr>
<tr>
<td>
Left</td><td>
Navigates up and left.</td></tr>
<tr>
<td>
Right</td><td>
Navigates down and right.</td></tr>
<tr>
<td>
Home</td><td>
Navigates to the starting item.</td></tr>
<tr>
<td>
End</td><td>
Navigates to the ending item.</td></tr>
<tr>
<td>
Enter</td><td>
Selects the focused item</td></tr>
</table>


In an ASPX page, add the following code example and set the AllowKeyboardNavigation property to true.

{% highlight html %}



<div class="frame">

        <ej:Rotator ID="Keyboardevent"  SlideWidth="550px"

            FrameSpace="0px" 

            DisplayItemCount="1"

            SlideHeight="350px" 

            PagerPosition="Outside"

            ShowThumbnail="true"

            ThumbnailSourceID="slide"

            Orientation="Horizontal"

            AllowKeyboardNavigation="true"

            runat="server">

            <Items>

                <ej:RotatorItem Caption="Nature" Url="../images/rotator/nature.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Beautiful Bird" Url="../images/rotator/bird.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Amazing Sculptures" Url="../images/rotator/sculpture.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Sea-View" Url="../images/rotator/seaview.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Snow Fall" Url="../images/rotator/snowfall.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Credit Card" Url="../images/rotator/card.jpg"></ej:RotatorItem>

            </Items>

            <Items>

                <ej:RotatorItem Caption="Colorful Night" Url="../images/rotator/night.jpg"></ej:RotatorItem>

            </Items>

        </ej:Rotator>



        <ul id="slide" style="display: none">

            <li>

                <img src="../images/rotator/nature.jpg" title="Nature" /></li>

            <li>

                <img src="../images/rotator/bird.jpg" title="Beautiful Bird" /></li>

            <li>

                <img src="../images/rotator/sculpture.jpg" title="Amazing Sculptures" /></li>

            <li>

                <img src="../images/rotator/seaview.jpg" title="Sea-View" /></li>

            <li>

                <img src="../images/rotator/snowfall.jpg" title="Snow Fall" /></li>

            <li>

                <img src="../images/rotator/card.jpg" title="Credit Card" /></li>

            <li>

                <img src="../images/rotator/night.jpg" title="Colorful Night" /></li>

        </ul>

    </div>



{% endhighlight %}



Add the following code in your JavaScript to focus the control.

{% highlight js %}

        $(function () {



            //Control focus key

            $(document).on("keydown", function (e) {

                if (e.altKey && e.keyCode === 74) { // j- key code.

                    $("#<%=Keyboardevent.ClientID%>")[0].focus();

                }

            });

        });


{% endhighlight %}


The following screenshot displays the output of the above code example.

![](Keyboard-interaction_images/Keyboard-interaction_img1.png)



