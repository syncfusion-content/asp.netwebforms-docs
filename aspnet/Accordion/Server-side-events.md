---
layout: post
title: Server side events | Accordion | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Accordion 
documentation: ug
---

# Server side events

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Parameters</th></tr>
<tr>
<td>
OnAccordionPaneClick</td><td>
Event is triggered when the accordion pane is clicked.</td><td>
(Object Sender, AccordionEventArgs e)Values passed in argument are as below,ActiveIndex - to get the activated pane indexEventType - returns the event name</td></tr>
</table>

The following steps explains you on how to define server side event for an Accordion control.

In an ASPX page, define the Accordion control and add the contents correspondingly.

{% highlight html %}



<div style="width: 400px;">

    <ej:Accordion ID="BasicAccordion" runat="server" OnAccordionPaneClick="BasicAccordion_AccordionPaneClick">

        <Items>

            <ej:AccordionItem Text="Orubase">

                <ContentSection>

                     Orubase is the only mobile application development Framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible time frame. 

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

In the code behind, define the action to be performed under the Accordion pane click event.



{% highlight c# %}



protected void BasicAccordion_AccordionPaneClick(object sender, Syncfusion.JavaScript.Web.AccordionEventArgs e)

{

    // e.ActiveIndex - to get the activated pane index

    // e.EventType - returns the event name

}



{% endhighlight %}





