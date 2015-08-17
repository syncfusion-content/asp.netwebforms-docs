---
layout: post
title: Keyboard-Navigation
description: keyboard navigation
platform: aspnet
control: Accordion 
documentation: ug
---

# Keyboard Navigation

You can use Keyboard shortcut keys as an alternative to the mouse while using Accordion control by using AllowKeyboardNavigation property. You have to focus the control to enable the keyboard navigation. Accordion control allows you to perform all kind of actions by using keyboard shortcuts.

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }}+ j	</td><td>
Focuses into the accordion control</td></tr>
<tr>
<td>
Up</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Down</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Left</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Right</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Home</td><td>
Moves to the first accordion panel</td></tr>
<tr>
<td>
End</td><td>
Moves to the last accordion panel</td></tr>
</table>


## Configure keyboard interaction

The following steps explains you on how to enable keyboard interaction for an Accordion control.

In an ASPX page, define the Accordion control and add the contents correspondingly.

{% highlight html %}


<div style="width: 400px;">

    <ej:Accordion ID="BasicAccordion" runat="server" AllowKeyboardNavigation="true">

        <Items>

            <ej:AccordionItem Text="Orubase">

                <ContentSection>

                     Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe. 

                </ContentSection>

            </ej:AccordionItem>

            <ej:AccordionItem Text="WinRT XAML">

                <ContentSection>

                    Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.

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

Output for Accordion control focused and navigated to last item by using Keyboard navigation is as follows.

 ![](Configure-keyboard-interaction_images/Configure-keyboard-interaction_img1.png)