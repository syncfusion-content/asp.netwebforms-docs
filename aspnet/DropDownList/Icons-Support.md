---
layout: post
title: Icons-Support
description: icons support 
platform: aspnet
control: DropDownList
documentation: ug
---

# Icons Support 

You can add the icons or images with list items in DropDown popup by using sprite CSS class. The following steps explain the configuration about the icons support with the DropDownList.

N> Images for this sample are available in ‘installed location /themes/images’ and you need to define images in the mentioned CSS. Henceforth, the images are displayed. 


In an ASPX page, add an element to configure the DropDownList.

{% highlight html %}

<div class="control">

    <ej:DropDownList ID="dropdownlist" TargetID="mailtoolslist" runat="server">

    </ej:DropDownList>

    <div id="mailtoolslist">

        <ul>

            <li>

                <div class="mailtools categorize">

                </div>

                Categorize and Move</li>

            <li>

                <div class="mailtools done">

                </div>

                Done</li>

            <li>

                <div class="mailtools flag">

                </div>

                Flag & Move</li>

            <li>

                <div class="mailtools forward">

                </div>

                Forward</li>

            <li>

                <div class="mailtools movetofolder">

                </div>

                Move to Folder</li>

            <li>

                <div class="mailtools newmail">

                </div>

                New E-mail</li>

            <li>

                <div class="mailtools meeting">

                </div>

                New Meeting</li>

            <li>

                <div class="mailtools reply">

                </div>

                Reply & Delete</li>

        </ul>

    </div>

</div>



{% endhighlight %}



Configure sprite CSS styles to the DropDownList.

{% highlight css %}

    /*controls*/

    .mailtools

    {

        display: block;

        background-image: url('../images/iconsapps.png');

        height: 25px;

        width: 25px;

        background-position: center center;

        background-repeat: no-repeat;

    }



    .mailtools.done

    {

        background-position: 0 0;

    }



    .mailtools.movetofolder

    {

        background-position: 0 -22px;

    }



    .mailtools.categorize

    {

        background-position: 0 -46px;

    }



    .mailtools.flag

    {

        background-position: 0 -70px;

    }



    .mailtools.forward

    {

        background-position: 0 -94px;

    }



    .mailtools.newmail

    {

        background-position: 0 -116px;

    }



    .mailtools.reply

    {

        background-position: 0 -140px;

    }



    .mailtools.meeting

    {

        background-position: 0 -164px;

    }



    .control

    {

        margin-left: 20px;

    }



    .ctrllabel

    {

        padding-bottom: 3px;

    }





{% endhighlight %}



Output of the above step.



![](Icons-Support_images/Icons-Support_img2.png)  



