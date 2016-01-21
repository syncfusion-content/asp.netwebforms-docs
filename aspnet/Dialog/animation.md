---
layout: post
title: animation
description: animation
platform: js
control: Control Name undefined
documentation: ug
---

## Animation

The Dialog widget can be animated while opening and closing the dialog.

We can specify the effect and the duration for the animation. There are two types of effects (slide and fade). We can configure these settings separately for open and close dialog actions.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ActionButtons="close,maximize,minimize,collapsible" EnableAnimation="true" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

        <Animation>

            <%--animation settings while opening the dialog--%>
            <Show Duration="500" Effect="slide" />

            <%--animation settings while closing the dialog--%>
            <Hide Duration="500" Effect="fade" />

        </Animation>

    </ej:Dialog>



{% endhighlight %}



![Animation](animation_images\animation_img1.png)

