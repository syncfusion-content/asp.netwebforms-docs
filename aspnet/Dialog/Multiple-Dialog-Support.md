---
layout: post
title: Multiple-Dialog-Support
description: multiple dialog support
platform: aspnet
control: Dialog
documentation: ug
---

# Multiple Dialog Support

The Dialog supports multiple controls in the same web page. You can use more number of Dialog controls with different content and different functionalities in the same web page.

## Configure Multiple Dialog

The following steps explain how to apply multiple Dialogs in the same web page. 

In the ASPX page, add the Dialog controls with Position.

{% highlight html %}



    <ej:Dialog ID="mvcdialog" runat="server" Title="MVC">

        <Position XValue="296" YValue="207" />

        <DialogContent>

            <div>

                <p>

                    Essential Studio for ASP.NET MVC contains all the controls you need to build line-of-business web applications including grids, charts, gauges, menus, calendars, editors, and much more.

                </p>

            </div>

        </DialogContent>

    </ej:Dialog>



    <ej:Dialog ID="orubasedialog" runat="server" Title="Orubase">

        <Position XValue="721" YValue="207" />

        <DialogContent>

            <div>

                <p>

                    Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe. 

                </p>

            </div>

        </DialogContent>

    </ej:Dialog>



    <ej:Dialog ID="winrtdialog" runat="server" Title="WinRT">

        <Position XValue="500" YValue="407" />

        <DialogContent>

            <div>

                <p>

                    Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. 

                               It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

                </p>

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}



The following screenshot is displays multiple Dialog controls in the same page.



![](Multiple-Dialog-Support_images/Multiple-Dialog-Support_img1.png) 
{:.image }


