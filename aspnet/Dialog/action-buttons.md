---
layout: post
title: action-buttons
description: action buttons
platform: js
control: Control Name undefined
documentation: ug
---

## Action Buttons

The Dialog widget provides the following action buttons.

1. Close

2. Maximize

3. Minimize

4. Pin/Unpin

5. Collapse/Expand

You can display only the necessary buttons in the Dialog widget by configuring the “ActionButtons” property.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ActionButtons="close,maximize,minimize" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

    </ej:Dialog>



{% endhighlight %}



![Action Buttons](action-buttons_images\action-buttons_img1.png)

