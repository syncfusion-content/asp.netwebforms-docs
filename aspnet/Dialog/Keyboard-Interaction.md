---
layout: post
title: Keyboard-Interaction
description: keyboard interaction
platform: aspnet
control: Dialog
documentation: ug
---

# Keyboard Interaction

The Dialog allows you to interact with the keyboard actions instead of mouse actions. All the Dialog actions can be achieved by using Keyboard shortcuts.


<table>
<tr>
<td>
Shortcut Keys</td><td>
Description</td></tr>
<tr>
<td>
Alt + j	</td><td>
Focuses the Dialog control.</td></tr>
<tr>
<td>
Up</td><td>
Dialog moves up.</td></tr>
<tr>
<td>
Down</td><td>
Dialog moves down.</td></tr>
<tr>
<td>
Right</td><td>
Dialog moves right.</td></tr>
<tr>
<td>
Left</td><td>
Dialog moves left.</td></tr>
<tr>
<td>
Esc</td><td>
Dialog window closes.</td></tr>
</table>

## Configure Keyboard Interaction

The following steps explain how to enable keyboard interaction for Dialog control.

In the ASPX page, add the Dialog control by using the following codes.

{% highlight html %}





    <ej:Dialog ID="dialog" runat="server" Width="550" Title="WinRT">

        <DialogContent>

            <div>

                Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications <span>including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more.</span>

                It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}

Set the focus key to the Dialog control

{% highlight js %}



    $(document).on("keydown", function (e)

    {

        if (e.altKey && e.keyCode === 74)

        { // j- key code.

$("#<%=dialog.ClientID%>").focus();

        }

    });





{% endhighlight %}

Run the sample and press Alt + j key to focus the Dialog control. You can perform the specified option by using the keyboard shortcuts.

