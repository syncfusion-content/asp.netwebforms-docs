---
layout: post
title: Dialog How To | Dialog | ASP.NET Webforms | Syncfusion
description: How to load content to dialog widget either using the Ajax, iframe, and Image.
platform: aspnet
control: Dialog
documentation: ug
keywords: ejdialog, ASP Dialog, ASP.NET Dialog, ASP.NET Web Dialog, EJ ASP.NET Dialog, Dialog ui, Web Dialog, ej Dialog, Dialog control
---

# How To?

## Create Multiple Dialogs

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
            <p>This is a different Dialog</p>
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



N> If the position of the dialog is not set as above, all the three dialogs will be overlapped with each other.

![Create Multiple Dialogs](how-to_images\create-multiple-dialogs_img1.png)



## Create Nested Dialog

A Dialog widget can be nested within another Dialog widget.

Create a div element to render the child Dialog widget and use it as a content of parent Dialog widget.

{% highlight html %}


    <ej:Button ID="outerbutton" Text="Open Dialog" Type="Button" ClientSideOnClick="openDialog" runat="server"></ej:Button>

    <ej:Dialog ID="outerDialog" Title="Dialog" ShowOnInit="false" Height="400px" Width="500px" runat="server">

        <DialogContent>

            <ej:Button ID="innerbutton" Text="Open Nested Dialog" Type="Button" ClientSideOnClick="openNestedDialog" runat="server"></ej:Button>

            <ej:Dialog ID="innerDialog" Title="Nested Dialog" ShowOnInit="false" Height="300px" Width="400px" runat="server">

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
            $("#MainContent_outerDialog").ejDialog("open");
        }
        function openNestedDialog() {
            $("#MainContent_outerDialog_innerDialog").ejDialog("open");
        }
    </script>



{% endhighlight %}

## Create Confirmation Dialog with Footer Option

Essential JS library supports Alert Dialog widgets.

Using `ShowFooter` property to render Alert Dialog with Footers in Dialog widget.

Create a Dialog Widget with enabling Footer property.

{% highlight html %}

        <div class="control">    
             <ej:Button ID="btnOpen" runat="server" Size="Medium" Type="Button" Height="30" Width="150" ClientSideOnClick="onOpen" Text="Click to open dialog"></ej:Button> 
             <ej:Dialog ID="basicDialog" Title="Software Installation Agreement" runat="server" ClientSideOnCreate="onCreate" Target=".control" ShowFooter="True" FooterTemplateId="sample" ClientSideOnClose="onDialogClose">
                <DialogContent>
                    <div class="cnt">
                       Do you really leave the session?                                
                    </div>
                </DialogContent>
        </ej:Dialog>
    </div>
	
{% endhighlight %}

Add the following script to open and close the Dialog widget.

{% highlight javascript %}

    $("#btnOpen").hide();
    function onDialogClose(args) {
        $("#btnOpen").show();
    }
    function onOpen() {
        $("#btnOpen").hide();
        $("#basicDialog").ejDialog("open");
	});

{% endhighlight %}

Initialize Footer in Dialog widgets by adding the script section in JsRender as below.

{% highlight javascript %}

    <script id="sample" type="text/x-jsrender">

	<div class="footerspan" style="float:right">
	
        <ej:Button ID="btn1" runat="server" Size="Mini" Height="30" Width="70" Text="Ok"></ej:Button>
		  
        <ej:Button ID="btn2" runat="server" Size="Mini" Height="30" Width="70" Text="Cancel"></ej:Button>
		  
    </div>
    <div class="condition" style="float:left; margin-left:15px">
  
        <ej:CheckBox ID="check1" runat="server" Text="Dont ask me this again"></ej:CheckBox>
  
    </div>
 
{% endhighlight %}

![Create Alert Dialog](how-to_images\dialog-footer1.png)



