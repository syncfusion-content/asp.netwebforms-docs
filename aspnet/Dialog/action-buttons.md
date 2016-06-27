---
layout: post
title: Dialog Action Buttons | Dialog | ASP.NET Webforms | Syncfusion
description: How to enable the Interaction button like “Close”, “Minimize” and etc., in Dialog Widget. 
platform: aspnet
control: Dialog
documentation: ug
keywords: ejdialog, ASP Dialog, ASP.NET Dialog, ASP.NET Web Dialog, EJ ASP.NET Dialog, Dialog ui, Web Dialog, ej Dialog, Dialog control
---

# Action Buttons

The Dialog widget provides the following action buttons.

1. Close

2. Maximize

3. Minimize

4. Pin/Unpin

5. Collapse/Expand

You can display only the necessary buttons in the Dialog widget by configuring the `ActionButtons` property.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ActionButtons="close,maximize,minimize" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

    </ej:Dialog>



{% endhighlight %}



![Action Buttons](action-buttons_images\action-buttons_img1.png)

## Customizing Action Buttons

We can customize the action buttons in dialog widget.

You can add new action button in the dialog widget by configuring the `actionButtonClick` event.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" ActionButtons="close,maximize,minimize,collapsible,pin,mediaplay,search" ClientSideOnActionButtonClick="playMedia" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

    </ej:Dialog>

{% endhighlight %}


{% highlight javascript %}
          
		  function playMedia(args)
		    {
               console.log(args.buttonID);
            }
			
{% endhighlight %}



![Action Buttons](action-buttons_images\action-buttons_img2.png)

