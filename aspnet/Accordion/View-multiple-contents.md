---
layout: post
title: View multiple contents | Accordion | ASP.NET Webforms |Syncfusion
description: view multiple contents
platform: aspnet
control: Accordion 
documentation: ug
---

# View multiple contents

By default Accordion allows only one panel to be in expanded state. You can enable multiple panels in expand state by setting EnableMultipleOpen to true.

## Enabling multiple panel open

The following steps explains you to enable multiple panel for Accordion.

In an ASPX page, define a <div> element that is a container for Accordion control and add the contents correspondingly.

{% highlight html %}



<div style="width:400px">     

    <ej:Accordion ID="BasicAccordion" runat="server" EnableMultipleOpen="true">

    <Items>

        <ej:AccordionItem Text="Orubase">

            <contentsection>

                Orubase is the only mobile application development Framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible time frame. 

            </contentsection>

        </ej:AccordionItem>

        <ej:AccordionItem Text="WinRT XAML">

            <contentsection>

                Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, PDF viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

            </contentsection>

        </ej:AccordionItem>

        <ej:AccordionItem Text="Metro Studio">

            <contentsection>

                Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons. 

            </contentsection>

        </ej:AccordionItem>

    </Items>

    </ej:Accordion>

</div>



{% endhighlight %}

Following screenshot is the output for Accordion control on EnableMultipleOpen set to true.

 ![Multiple panel](View-multiple-contents_images/View-multiple-contents_img1.png)





