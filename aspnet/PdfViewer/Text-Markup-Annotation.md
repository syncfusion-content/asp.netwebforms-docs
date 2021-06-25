---
layout: post
title: Text markup annotation | ASP.NET Webforms PDF viewer | Syncfusion
description: Learn about text markup annotation support in Syncfusion ASP.NET Webforms PDF viewer control and more details.
platform: aspnet
control: PDF viewer
documentation: ug
---

# Text Markup Annotation in ASP.NET Web Forms PDF Viewer

The PDF viewer control supports adding text markup annotations in the PDF documents. The control also renders the existing text markup annotations from the PDF document when the document is loaded in it.

The text markup annotation tools in the default toolbar can be enabled or disabled using the toolbarSettings property.

The following code snippet describes how to show only the text markup annotation tools in the control.

{% highlight c# %}
protected void Page_Load(object sender, EventArgs e)
        {
            PdfViewer1.ToolbarSettings = new Syncfusion.JavaScript.Models.PDFViewer.PdfViewerToolbarSettings();
            PdfViewer1.ToolbarSettings.Items = Syncfusion.JavaScript.PdfViewerEnums.ToolbarItems.TextMarkupAnnotationTools;
        }
{% endhighlight %}

The following screenshot shows the PDF viewer with the PDF documents containing text markup annotations:

![Text markup annotation icon](Text-Markup-Annotation_images/Text_Markup_Annotations_img1.png)

**Enable or Disable the text markup annotations**

The adding and modifying of the text markup annotations can be enabled or disabled using the EnableTextMarkupAnnotations property.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" EnableTextMarkupAnnotations="true"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
{% endhighlight %}

The adding and modifying of the highlight annotations can be enabled or disabled using the EnableHighlightAnnotation property.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" EnableHighlightAnnotation="true"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
{% endhighlight %}

The adding and modifying of the strikethrough annotations can be enabled or disabled using the EnableStrikethroughAnnotation property.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" EnableStrikethroughAnnotation="true"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
{% endhighlight %}

The adding and modifying of the underline annotations can be enabled or disabled using the EnableUnderlineAnnotation property.

{% highlight javascript %}
  <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" EnableUnderlineAnnotation="true"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
{% endhighlight %}

**Providing settings for text markup annotations**

You can get or set the settings of the highlight annotations using the highlightSettings property. The highlightSettings property is used to set the color, opacity, author, subject, modifiedDate and isLocked properties of the highlight annotations.

{% highlight c# %}
protected void Page_Load(object sender, EventArgs e)
        {
            PdfViewer1.HighlightSettings = new Syncfusion.JavaScript.Models.PDFViewer.PdfViewerHighlightSettings();
            PdfViewer1.HighlightSettings.Color = "#ffff00";
            PdfViewer1.HighlightSettings.Author = "Guest";
            PdfViewer1.HighlightSettings.Opacity = 0.5f;
            PdfViewer1.HighlightSettings.ModifiedDate = "2017-03-27 12:00:51";
            PdfViewer1.HighlightSettings.Subject = "highlight";
            PdfViewer1.HighlightSettings.IsLocked = true;
        }
{% endhighlight %}

You can get or set the settings of the strikethrough annotations using the strikethroughSettings property. The strikethroughSettings property is used to set the color, opacity, author, subject, modifiedDate, and isLocked properties of the strikethrough annotations.

{% highlight c# %}
   protected void Page_Load(object sender, EventArgs e)
        {
            PdfViewer1.StrikethroughSettings = new Syncfusion.JavaScript.Models.PDFViewer.PdfViewerStrikethroughSettings();
            PdfViewer1.StrikethroughSettings.Color = "#ffff00";
            PdfViewer1.StrikethroughSettings.Author = "Guest";
            PdfViewer1.StrikethroughSettings.Opacity = 0.5f;
            PdfViewer1.StrikethroughSettings.ModifiedDate = "2017-03-27 12:00:51";
            PdfViewer1.StrikethroughSettings.Subject = "highlight";
            PdfViewer1.StrikethroughSettings.IsLocked = true;
        }
{% endhighlight %}

You can get or set the settings of the underline annotations using the underlineSettings property. The underlineSettings property is used to set the color, opacity, author, subject, modifiedDate, and isLocked properties of the underline annotations.

{% highlight javascript %}
  protected void Page_Load(object sender, EventArgs e)
        {
            PdfViewer1.UnderlineSettings = new Syncfusion.JavaScript.Models.PDFViewer.PdfViewerUnderlineSettings();
            PdfViewer1.UnderlineSettings.Color = "#ffff00";
            PdfViewer1.UnderlineSettings.Author = "Guest";
            PdfViewer1.UnderlineSettings.Opacity = 0.5f;
            PdfViewer1.UnderlineSettings.ModifiedDate = "2017-03-27 12:00:51";
            PdfViewer1.UnderlineSettings.Subject = "highlight";
            PdfViewer1.UnderlineSettings.IsLocked = true;
        }
{% endhighlight %}

**Adding text markup annotations**

The text markup annotations are added to the PDF document using the text markup annotation tools provided in the toolbar of the PDF viewer control.

The annotations can be added to the PDF document from the client side using the annotationType property and addAnnotation method.

{% highlight javascript %}
var pdfviewerObj = $("#pdfviewer").data("ejPdfViewer");
pdfviewerObj.addAnnotation(ej.PdfViewer.AnnotationType.Underline);
{% endhighlight %}

The colorpicker control is provided in the text markup annotation tools to select the desired color for the text markup annotation to be added in the document.

![Text markup annotation colorpicker](Text-Markup-Annotation_images/Text_Markup_Annotations_img2.png)

When the text markup annotation is added in the PDF document, the annotationAdd event will be triggered in the control. The event method can be defined using the AnnotationAdd property of the control.

{% highlight javascript %}
 <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" AnnotationAdd="annotationAdded"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

        function annotationAdded(args) {
            alert("A text markup annotation is added in the PDF document”);
        }

{% endhighlight %}

**Adding notes to the text markup annotation**

The notes can be added to the text markup annotations using the context menu  in the PDF viewer control.

Right click the text markup annotation in the PDF document, the context menu will be opened in the PDF viewer control. You can select the option **Open Pop-up Note** to add the note to the annotation.

The following screenshot shows that the notes have been added to a text markup annotation in the PDF document:

![Text markup annotation notes](Text-Markup-Annotation_images/Text_Markup_Annotations_img3.png)

**Editing the text markup annotation**

The properties of the text markup annotations in the PDF document can be edited using the properties window provided in the PDF viewer control. The color, opacity, author, and subject of the text markup annotation can be modified. The properties of the text markup annotation can also be locked using the locked checkbox in the properties window.

N> The isLocked property of the text markup annotation will lock the properties of the selected annotation. The property of the text markup annotation can be modified once the isLocked property is disabled.

When a property of the text markup annotation is changed in the PDF viewer control, annotationPropertiesChange event will be triggered in the control. The event method can be defined using the AnnotationPropertiesChange property of the control.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" AnnotationPropertiesChange="annotationPropertiesChanged"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

function annotationPropertiesChanged(args) {
            alert("The properties of a text markup annotation is modified in the PDF viewer”);
        }
{% endhighlight %}

The following screenshot shows the properties window used for editing the properties of a text markup annotation:

![Text markup annotation properties](Text-Markup-Annotation_images/Text_Markup_Annotations_img4.png)

The annotationDelete event will be triggered in the control when the text markup annotation in the PDF document is deleted. The event method can be defined using the AnnotationDelete property of the control.

{% highlight javascript %}
  <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" AnnotationRemove="annotationRemoved"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer
function annotationRemoved (args) {
            alert("A text markup annotation is deleted in the PDF document”);
        }
{% endhighlight %}

You can undo and redo the changes made to text markup annotations included in the PDF documents using the undo() and redo() methods.

{% highlight javascript %}
 function undoChanges() {
        $(“#pdfviewer”).data(“ejPdfViewer”).undo();
    }
    function redoChanges() {
        $(“#pdfviewer”).data(“ejPdfViewer”).redo();
    }
{% endhighlight %}

**Saving the text markup annotation**

When the download tool is selected in the toolbar, the text markup annotations will be saved in the PDF document. This action will not affect the original document.

**Printing the text markup annotation**

When the print tool is selected in the toolbar, the PDF document will be printed along with the text markup annotations added to the pages. This action will not affect the original document.
