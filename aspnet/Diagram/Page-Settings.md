---
layout: post
title: Customize the size and appearance of single or multiple Diagram pages
description: How to customize the size and appearance of the Diagram pages?
platform: aspnet
control: Diagram
documentation: ug
---


# Page Settings 

Page settings enable to customize the appearance, width, and height of the Diagram page.

![](/aspnet/Diagram/Page-Settings_images/Page-Settings_img1.png)

## Page size and appearance

The size and appearance of the Diagram pages can be customized with the `PageSettings` property. 

The `PageWidth` and `PageHeight` properties of page settings define the size of the page. In addition to that, you can customize the appearance of the page with a set of appearance specific properties.
To explore those properties, refer [Page Settings](/aspnet/api/Diagram#members:pagesettings "Page Settings").

You can also customize the appearance of off-page regions with the property `BackgroundColor`.

The following code illustrates how to customize the page size and the appearance of page and off-page.

{% highlight ASPX %}

        <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px">
            <%-- Sets page size and Customizes the appearance of page--%>
            <PageSettings PageHeight="500" PageWidth="500" PageBorderWidth="4"
                PageBackgroundColor="white" PageBorderColor="lightgray" PageMargin="24"
                ShowPageBreak="true" MultiplePage="true" PageOrientation="Portrait"></PageSettings>
        </ej:Diagram>
{% endhighlight %}


![](/aspnet/Diagram/Page-Settings_images/Page-Settings_img2.png)

![](/aspnet/Diagram/Page-Settings_images/Page-Settings_img3.png)

N>When the PageWidth and PageHeight are not specified, the rectangular region that completely fits all nodes and connectors are considered as page size.

## MultiplePage and PageBreaks

When MultiplePage is enabled, size of the page dynamically increases or decreases in multiples of page width and height and completely fits diagram within the page boundaries. Page Breaks is used as a visual guide to see how pages are split into multiple pages.

![](/aspnet/Diagram/Page-Settings_images/Page-Settings_img4.png)

`MultiplePage` and `ShowPageBreak` properties of page settings allow you to enable/disable multiple pages and page breaks respectively.
The following code illustrates how to enable multiple page and page break lines.

{% highlight ASPX %}

     <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px">
            <%-- Enables the multiple page and the page break lines --%>
            <PageSettings ShowPageBreak="true" MultiplePage="true" PageOrientation="Portrait"></PageSettings>
        </ej:Diagram>

{% endhighlight %}

## Boundary Constraints

 Diagram provides support to restrict/customize the interactive region, out of which the elements cannot be dragged, resized or rotated. 
 `BoundaryConstraints` property of page settings allows you to customize the interactable region. To explore the boundary constraints, refer refer [Boundary Constraints](/aspnet/api/Diagram#members:boundaryConstraints "Boundary Constraints").

The following code example illustrates how to define boundaryConstraints.

{% highlight ASPX %}


        <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px">
            <%-- Allows to drag within the diagram content --%>
            <PageSettings BoundaryConstraints="Diagram"></PageSettings>
        </ej:Diagram>

    
{% endhighlight %}