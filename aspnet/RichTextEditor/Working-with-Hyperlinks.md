---
layout: post
title: Working with hyperlink customization | RTE |Syncfusion| ASP.NET
description: Working with Hyperlinks customization in RichTextEditor control
platform: aspnet
control: RTE
documentation: ug
keywords: RichTextEditor, Hyperlinks

---
# Working with Hyperlinks

A hyperlink can be inserted into the editor for quick access to the related information. The hyperlink itself can be a text or an image.

## Add and Edit a hyperlink

To add a hyperlink to the editor, follow these instructions:

1. Point the cursor anywhere within the editor where you’d like to insert the link. It is also possible to select a text or an image within the editor and can be converted to the hyperlink.
2. Click the “Insert/Edit hyperlink” tool on the Toolbar.
3. In the **Web** **Address** box, type or paste the destination for the link you are creating.
4. In the **Text** box, type or edit the required text that you want to display text for the link. 

N> Leave this textbox blank if you want to display the full link as hyperlink in the editor.

5. To display additional helpful information when you place the pointer on the hyperlink, type the required text in the “Tooltip” field.
6. Click OK button to insert a hyperlink.

{% highlight html %}

<ej:RTE ID="RTE2" runat="server" ToolsList="links">
    <RTEContent>
        <ul>
            <li>The Rich Text Editor  (RTE) control is an easy to render in client side. </li>
            <li>Customer easy to edit the contents and get the HTML content for the displayed content. </li>
            <li> A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered  in the text area.</li>
        </ul>       
    </RTEContent>
    <Tools Links="createLink,removeLink"> </Tools>
</ej:RTE>

{% endhighlight %}

N> hyperlinks on a picture are not always visible, but the pointer’s appearance will be changed on positioning the mouse pointer over it.

## Remove a hyperlink

If you want to remove a hyperlink from a text or image, select the text or image with the hyperlink and click “Remove Hyperlink” tool from toolbar. It will keep the text or image.