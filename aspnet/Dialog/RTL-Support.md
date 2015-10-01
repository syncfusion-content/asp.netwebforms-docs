---
layout: post
title: RTL Support | Dialog | ASP.NET Webforms | Syncfusion
description: rtl support
platform: aspnet
control: Dialog
documentation: ug
---

# RTL Support

The Dialog supports Right-To-Left feature. The alignment of Dialog content can be changed from Left-To-Right to Right-To-Left alignment.

## Enable RTL Support

The following steps explain enabling the right-to-left property of the Dialog control.

In the ASPX page, add the Dialog control and set the EnableRTL to true.

{% highlight html %}



    <ej:Dialog ID="rtldialog" runat="server" Width="550" Title="WinRT" EnableRTL="true">

        <DialogContent>

            <div>

                Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications <span>including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more.</span>

                It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

            </div>

        </DialogContent>

    </ej:Dialog> 





{% endhighlight %}



The screenshot displays Dialog when EnabelRTL is set to true.

![](RTL-Support_images/RTL-Support_img1.png) 



