---
layout: post
title: InteractionMode | PDF viewer | ASP .NET | Syncfusion
description: InteractionMode | PDF viewer | ASP .NET | Syncfusion
platform: aspnet
control: PDF viewer
documentation: ug
---

# Interaction Mode

The PDF viewer control provides interaction modes for easy interaction with the PDF documents in the control. Selection mode and Panning mode are the two interaction modes.

### Selection Mode

In this mode, the text selection can be performed in the PDF document loaded in the PDF viewer control. The panning and scrolling of the pages by touch cannot be performed in this mode.

![Interaction mode select](Interaction-Mode_images/InteractionMode_1.jpeg)

### Enable or disable the Text selection

The text selection in the PDF viewer control can be enabled or disabled using the EnableTextSelection property.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" EnableTextSelection="true"
            runat="server">
        </ej:pdfviewer>
{% endhighlight %}

### Panning Mode

In this mode, the panning and scrolling of the pages by touch can be performed in the PDF document loaded in the PDF viewer control, but the text selection cannot be performed.

![Interaction mode pan](Interaction-Mode_images/InteractionMode_2.jpeg)