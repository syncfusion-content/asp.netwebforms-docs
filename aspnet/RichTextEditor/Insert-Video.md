---
layout: post
title: Insert-Video
description: insert video 
platform: aspnet
control: RichTextEditor
documentation: ug
---

# Insert Video 

Videos can be included in RTE by rendering the embedded code of a video. In some cases, you have to add the video in your blog to provide more information about your product. Consider product installation steps need to be given in a video format. You can use the “InsertVideo” tool item to insert the video in a blog.

Try the following code in the insert video dialog,

{% highlight html %}

    <video width="400" controls>

        <source src="mov_bbb.mp4" type="video/mp4">

        <source src="mov_bbb.ogg" type="video/ogg">

        Your browser does not support HTML5 video.

    </video>

{% endhighlight %}

![](Insert-Video_images/Insert-Video_img1.png)

> Note: Insert video option is enabled only in HTML5 support browsers.