---
layout: post
title: Configure keyboard interaction | Accordion | ASP.NET Webforms | Syncfusion
description: configure keyboard interaction
platform: aspnet
control: Accordion 
documentation: ug
---

# Configure keyboard interaction

The following steps explains you on how to enable keyboard interaction for an Accordion control.

In an ASPX page, define the Accordion control and add the contents correspondingly.

{% tabs %}

{% highlight html %}

<div style="width: 400px;">

    <ej:Accordion ID="BasicAccordion" runat="server" AllowKeyboardNavigation="true">

        <Items>

            <ej:AccordionItem Text="Orubase">

                <ContentSection>

                     Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible time frame. 

                </ContentSection>

            </ej:AccordionItem>

            <ej:AccordionItem Text="WinRT XAML">

                <ContentSection>

                    Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, PDF viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

                </ContentSection>

            </ej:AccordionItem>

            <ej:AccordionItem Text="Metro Studio">

                <ContentSection>

                    Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons. 

                </ContentSection>

            </ej:AccordionItem>

        </Items>

    </ej:Accordion>

    </div>





{% endhighlight %}



{% highlight js %}



    $(function () {

            $(document).on("keydown", function (e) {

                if (e.altKey && e.keyCode === 74) { // j- key code.

                    $("#<%=BasicAccordion.ClientID%>").focus();

                }

            });

        });



{% endhighlight %}

{% endtabs %}



Output for Accordion control focused and navigated to last item by using Keyboard navigation is as follows.

 ![](Configure-keyboard-interaction_images/Configure-keyboard-interaction_img1.png)



