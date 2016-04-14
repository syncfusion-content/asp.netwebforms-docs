---
layout: post
title: Dialog Getting Started | Dialog | ASP.NET Webforms | Syncfusion
description: How to create Dialog widget with the step-by-step instructions. 
platform: aspnet
control: Dialog
documentation: ug
keywords: ejdialog, ASP Dialog, ASP.NET Dialog, ASP.NET Web Dialog, EJ ASP.NET Dialog, Dialog ui, Web Dialog, ej Dialog, Dialog control
---

# Getting Started

This section helps to understand the getting started of the Dialog widget with the step-by-step instructions.

## Create a Dialog

Create an ASP Project and add the necessary DLL and scripts with the help of the given [ASP Getting Started](http://help.syncfusion.com/aspnet/getting-started) documentation.

Add the following code snippet to the corresponding ASPX page to render the Dialog.

{% highlight html %}


    <ej:Dialog ID="dialog" runat="server"></ej:Dialog>


{% endhighlight %}



![Create Dialog](getting-started_images\getting-started_img1.png)

### Set content

Add the contents for the dialog as below.

{% highlight html %}


    <ej:Dialog ID="dialog" runat="server">

        <DialogContent>
             <p>This is a simple dialog</p>
        </DialogContent>

    </ej:Dialog>


{% endhighlight %}

![Add dialog content](getting-started_images\getting-started_img2.png)

### Set Title

The Dialog widget’s title can be set as follows.

{% highlight html %}


    <ej:Dialog ID="dialog" Title="Dialog" runat="server">

        <DialogContent>
             <p>This is a simple dialog</p>
        </DialogContent>

    </ej:Dialog>


{% endhighlight %}

![Set the title](getting-started_images\getting-started_img3.png)

### Open Dialog dynamically

In most cases, the Dialog widgets are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So the Dialog widget provides “open” and “close” methods to open/close the dialogs dynamically.

The Dialog widget can be hidden on initialize using `ShowOnInit` property which should be set to false.

{% seealso %}

[Button](http://help.syncfusion.com/aspnet/button/getting-started).

{% endseealso %}


Refer the below example. The dialog will be opened on clicking the Button widget.

{% highlight html %}


    <%-- button widget --%>
    <ej:Button ID="button" Text="Open Dialog" Type="Button" ClientSideOnClick="openDialog" runat="server"></ej:Button>

    <ej:Dialog ID="dialog" Title="Dialog" ShowOnInit="false" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

    </ej:Dialog>



{% endhighlight %}

Add the following script

{% highlight js %}


    <script>
        function openDialog() {
            $("#MainContent_dialog").ejDialog("open");
        }
    </script>



{% endhighlight %}

![Open-Dialog-dynamically](getting-started_images\getting-started_img4.png)

