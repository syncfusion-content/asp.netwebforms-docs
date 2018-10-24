---
layout: post
title: Dialog Load content | Dialog | ASP.NET Webforms | Syncfusion
description: Content Loading in Dialog
platform: aspnet
control: Dialog
documentation: ug
keywords: ejdialog, ASP Dialog, ASP.NET Dialog, ASP.NET Web Dialog, EJ ASP.NET Dialog, Dialog ui, Web Dialog, ej Dialog, Dialog control
---

# Load content

By default, the content inside the DialogContent element is considered as the content for the Dialog widget.

Also, we can render the Dialog widget content through the following ways.

1. Request through AJAX

2. Request iframe content

3. Request image content

This settings can be specified through `ContentType` property.

N> Create an aspx file (AjaxContent.aspx) which contains the content of the dialog.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ContentType="ajax" ContentUrl="AjaxContent.aspx" runat="server"></ej:Dialog>



{% endhighlight %}



AjaxContent.aspx

{% highlight html %}


    <div id="content"> This content is loaded via AJAX request. </div>


{% endhighlight %}



![Load content](load-content_images\load-content_img1.png)

We can handle the AJAX request’s success and failures through the events `ClientSideOnAjaxSuccess` and `ClientSideOnAjaxError` events respectively. 

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



N> The same way we can render the iframe and image content for the Dialog widget by specifying the `ContentType` as “iframe” and “image” respectively and also by specifying the proper location in the “**ContentUrl**” property.  If you wish to dynamically change the dialog content, you can set the `ContentUrl` and the `ContentType` property through setModel on any action.
