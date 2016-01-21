---
layout: post
title: how-to
description: how to
platform: js
control: Control Name undefined
documentation: ug
---

## How To?

### Create Multiple Dialogs

Essential Studio for ASP.NET library supports multiple Dialog widgets in the same web page with different contents and different functionalities.

Initialize the Dialog widgets by configuring as below.

{% highlight html %}


    <ej:Dialog ID="firstdialog" Title="Dialog" Width="250" runat="server">

        <DialogContent>
            <p>This is a Dialog</p>
        </DialogContent>

        <Position XValue="20px" YValue="20px" />

    </ej:Dialog>

    <ej:Dialog ID="seconddialog" Title="Window" Width="250" runat="server">

        <DialogContent>
            <p>This is a diferent Dialog</p>
        </DialogContent>

        <Position XValue="300px" YValue="20px" />

    </ej:Dialog>

    <ej:Dialog ID="thirdialog" Title="PopUp" Width="250" runat="server">

        <DialogContent>
            <p>This is an another Dialog</p>
        </DialogContent>

        <Position XValue="150px" YValue="150px" />

    </ej:Dialog>



{% endhighlight %}



_**Note:**_ _If the position of the dialog is not set as above, all the three dialogs will be overlapped with each other._

![Create Multiple Dialogs](how-to_images\create-multiple-dialogs_img1.png)



### Create Nested Dialog

A Dialog widget can be nested within another Dialog widget.

Create a div element to render the child Dialog widget and use it as a content of parent Dialog widget.

{% highlight html %}


    <ej:Button ID="outerbutton" Text="Open Dialog" Type="Button" ClientSideOnClick="openDialog" runat="server"></ej:Button>

    <ej:Dialog ID="outerdialog" Title="Dialog" ShowOnInit="false" Height="400px" Width="500px" runat="server">

        <DialogContent>

            <ej:Button ID="innerbutton" Text="Open Nested Dialog" Type="Button" ClientSideOnClick="openNestedDialog" runat="server"></ej:Button>

            <ej:Dialog ID="innerdialog" Title="Nested Dialog" ShowOnInit="false" Height="300px" Width="400px" runat="server">

                <DialogContent>
                    <div>This is a nested Dialog</div>
                </DialogContent>

            </ej:Dialog>

        </DialogContent>

    </ej:Dialog>



{% endhighlight %}

Add the following script

{% highlight js %}


    <script>
        function openDialog() {
            $("#MainContent_outerdialog").ejDialog("open");
        }
        function openNestedDialog() {
            $("#MainContent_outerdialog_innerdialog").ejDialog("open");
        }
    </script>



{% endhighlight %}



