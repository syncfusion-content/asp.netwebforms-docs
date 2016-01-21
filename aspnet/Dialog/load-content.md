---
layout: post
title: load-content
description: load content
platform: js
control: Control Name undefined
documentation: ug
---

## Load content

By default, the content inside the DialogContent element is considered as the content for the Dialog widget.

Also, we can render the Dialog widget content through the following ways.

1. Request through Ajax

2. Request iframe content

3. Request image content

This settings can be specified through “ContentType” property.

_**Note**__: Create 	an aspx file (AjaxContent.aspx) which contains the content of the dialog._

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ContentType="ajax" ContentUrl="AjaxContent.aspx" runat="server"></ej:Dialog>



{% endhighlight %}



AjaxContent.aspx

{% highlight html %}


    <div id="content"> This content is loaded via AJAX request. </div>


{% endhighlight %}



![Load content](load-content_images\load-content_img1.png)

We can handle the AJAX request’s success and failures through the events “ClientSideOnAjaxSuccess” and “ClientSideOnAjaxError” events respectively. 

You can modify the previous example as below to handle the success and failure events.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ContentType="ajax" ClientSideOnAjaxSuccess="OnSuccess" ClientSideOnAjaxError="OnError" ContentUrl="AjaxContent.aspx" runat="server"></ej:Dialog>



{% endhighlight %}


Add the following script

{% highlight js %}


    <script>
        function onSuccess(args) {
            //handle success event
        }
        function onError(args) {
            //handle success event
        }
    </script>



{% endhighlight %}



_**Note:**_ _The same way we can render the iframe and image content for the Dialog widget by specifying the “__**ContentType**__” as “iframe” and “image” respectively and also by specifying the proper location in the “__**ContentUrl**__” property._



