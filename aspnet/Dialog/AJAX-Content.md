---
layout: post
title: AJAX-Content
description: ajax content
platform: aspnet
control: Dialog
documentation: ug
---

# AJAX Content

The Dialog provides AJAX content support where you can add the HTML content to the Dialog content. 

## Configure AJAX Content

The following steps explains how to implement AJAX content in the Dialog control. 

In the ASPX page, add the Dialog control and set the ContentUrl from the file reference and set ContentType as ajax.

{% highlight html %}





    <ej:Dialog ID="ajaxdialog" runat="server" ContentUrl="Content/twitter.html" ContentType="ajax" Title="Twitter">        

    </ej:Dialog>





{% endhighlight %}



Content in the twitter.html.



{% highlight html %}



<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head>

    <title></title>

    <style>



        .cont-list img {

            float: left;

            height: 40px;

            padding-right: 6px;

            padding-left: 6px;

        }



        .comments-list {

            /* background-color: #EFEFEF; */

            height: 210px;

        }



        .comments {

            padding: 10px;

            color: #074B92;

            font-weight: 600;

        }



        .cont-list {

            border-bottom: 1px solid #BBBCBB;

            padding-top: 9px;

            padding-bottom: 9px;

        }



            .cont-list:last-child {

                border-bottom: none;

                padding-bottom: 0;

            }



        .time-panel {

            float: right;

            color: #2382C3;

            margin-right: 10px;

        }



        .headername {

            font-size: 16px;

            font-weight: 600;

            color: #074B92;

        }



        .c-list {

            float: right;

            margin-top: -11px;

            padding-right: 12px;

        }

    </style>

</head>

<body>

    <div>

        <div class="comments-list">

            <div class="cont-list">

                <img src="Content/Images/8.png" alt="contact" />

                <div class="time-panel">1 hr</div>

                <b class="headername">Erik Linden</b><br />

                Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe. 

                <div class="comments">

                    <div class="c-list">Retweet</div>

                    <div class="c-list">Reply</div>

                    <div class="c-list">Share</div>

                </div>

            </div>

            <div class="cont-list">

                <img src="Content/Images/6.png" alt="contact" />

                <div class="time-panel">2 hr</div>

                <b class="headername">John Louis</b><br />

                All the components in the ASP.NET MVC Essential Studio have been built from the ground up with performance in mind and are extremely lightweight.

                 <div class="comments">

                     <div class="c-list">Retweet</div>

                     <div class="c-list">Reply</div>

                     <div class="c-list">Share</div>

                 </div>

            </div>

        </div>

    </div>

</body>

</html>





{% endhighlight %}



The output of Dialog with AJAX content.

![](AJAX-Content_images/AJAX-Content_img1.png) 



