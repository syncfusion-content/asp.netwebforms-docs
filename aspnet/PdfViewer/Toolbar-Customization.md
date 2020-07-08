---
layout: post
title: Toolbar customization of Syncfusion Essential ASP.NET PDF viewer.
description: Toolbar customization of Syncfusion Essential ASP.NET PDF viewer.
platform: aspnet
control: PDF viewer
documentation: ug
keywords: pdfviewer, PDF viewer
---

# Toolbar Customization

**Customizing default toolbar**

The default toolbar is grouped into the following set of tools.
<table>
<tr>
<td>
{{'**MagnificationTools**'| markdownify }}
</td>
<td>
Contains ZoomIn, ZoomOut, Zoom, FitPage and FitWidth tools.
</td>
</tr>
<tr>
<td>
{{'**NavigationTools**'| markdownify }}
</td>
<td>
Contains GoToNext and GoToLast tools.
</td>
</tr>
<tr>
<td>
{{'**PrintTools**'| markdownify }}
</td>
<td>
Contains print tool.
</td>
</tr>
<tr>
<td>
{{'**DownloadTool**'| markdownify }}
</td>
<td>
Contains download tool.
</td>
</tr>
<tr>
<td>
{{'**TextSearchTool**'| markdownify }}
</td>
<td>
Contains text search tool.
</td>
</tr>
<tr>
<td>
{{'**TextMarkupAnnotationTools**'| markdownify }}
</td>
<td>
Contains text markup annotation tools.
</td>
</tr>
<tr>
<td>
{{'**SignatureTool**'| markdownify }}
</td>
<td>
Contains signature tool.
</td>
</tr>
<tr>
<td>
{{'**SelectionTool**'| markdownify }}
</td>
<td>
Contains selection tool.
</td>
</tr>
</table>

The PDF viewer control has an option to show or hide these grouped items in the default toolbar. You can hide or display any of these tools by using the toolbarSettings property. The following code snippet describes how to show the magnification tools in the widget.

{% highlight c# %}
 protected void Page_Load(object sender, EventArgs e)
        {
            PdfViewer1.ToolbarSettings = new Syncfusion.JavaScript.Models.PDFViewer.PdfViewerToolbarSettings();
            PdfViewer1.ToolbarSettings.Items = Syncfusion.JavaScript.PdfViewerEnums.ToolbarItems.MagnificationTools;        
        }
{% endhighlight %}

The PDF viewer control also has an option to show or hide the complete default toolbar. You can achieve this by using the showToolbar(bool) method. The following code snippet describes how to hide the default toolbar in the widget.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showToolbar(false);
</script>
{% endhighlight %}

**Magnification tools**

The magnification tools of the PDF viewer contain ZoomIn, ZoomOut, Zoom, FitPage, and FitWidth tools in the default toolbar. The PDF viewer control also has an option to show or hide the magnification tools in the default toolbar. You can achieve this by using the showMagnificationTools(bool) method. The following code snippet describes how to hide the magnification tools in the default toolbar in the widget. 

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showMagnificationTools(false);
</script>
{% endhighlight %}

**APIs available for Magnification tools**

fitToPage()

You can fit the page size of the PDF document loaded in the PDF viewer control using the fitToPage() method. 

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).fitToPage();
</script>
{% endhighlight %}

fitToWidth()

You can fit the page width of the PDF document loaded in the PDF viewer control using the fitToWidth() method. 

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).fitToWidth();
</script>
{% endhighlight %}

zoomIn()

You can zoom the PDF document page loaded in the PDF viewer control using zoomIn() method. The maximum zoom percentage is 400%.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).zoomIn();
</script>
{% endhighlight %}

zoomOut()

You can zoom out the PDF document page loaded in the PDF viewer control using the zoomOut() method. The minimum zoom percentage is 50%.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).zoomOut();
</script>
{% endhighlight %}

zoomTo(zoomValue)

The PDF document page loaded in the PDF viewer control can be zoomed to a specific value using the zoomTo(zoomValue) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).zoomTo(200);
</script>
{% endhighlight %}

zoomPercentage

The zoomPercentage property of the PDF viewer control returns the current zoom value of the PDF document.

{% highlight javascript %}
<script>
    var pdfviewer = $(“pdfviewer”).data(“ejPdfViewer”);
    var zoomValue = pdfviewer. zoomPercentage;
</script>
{% endhighlight %}

**Navigation Tools**

The navigation tools of the PDF viewer contain GoToNext, GoToPrevious, and current page number tools in the default toolbar. The PDF viewer control also has an option to show or hide the navigation tools in the default toolbar. You can achieve this by using the showPageNavigationTools(bool) method. The following code snippet describes how to hide the navigation tools in the default toolbar in the widget.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showPageNavigationTools(false);
</script>
{% endhighlight %}

**APIs available for Navigation Tools**

goToPreviousPage()

The previous page of the PDF document from the current page can be navigated in the PDF viewer using goToPreviousPage() method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).goToPreviousPage();
</script>
{% endhighlight %}

goToNextPage()

The next page of the PDF document from the current page can be navigated in the PDF viewer using the goToNextPage() method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).goToNextPage();
</script>
{% endhighlight %}

goToFirstPage()

The first page of the PDF document can be navigated in the PDF viewer using the goToFirstPage() method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).goToFirstPage();
</script>
{% endhighlight %}

goToLastPage()

The last page of the PDF document can be navigated in the PDF viewer using the goToLastPage() method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).goToLastPage();
</script>
{% endhighlight %}

goToPage(pageNumber)

The specific page in the PDF document can be navigated using the goToPage(pageNumber) method. If the page is not available for the given pageNumber, the PDF viewer retains the existing page in view.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).goToPage(4);
</script>
{% endhighlight %}

**Text Markup Annotation Tools**

The text markup annotation tools of the PDF viewer contain strikeout, highlight, and underline tools in the default toolbar. The PDF viewer control also has an option to show or hide the text markup annotation tools in the default toolbar. You can achieve this by using the showTextMarkupAnnotationTools(bool) method. The following code snippet describes how to hide the text markup annotation tools in the default toolbar in the widget.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showTextMarkupAnnotationTools(false);
</script>
{% endhighlight %}

## Print Tool

The print tool of the PDF viewer contains an option to print the PDF document. When the print button is clicked, the changes made in the PDF document will be printed along with the document using the browser’s default printer settings. The PDF viewer control provides the option to show or hide the print tool in the default toolbar. You can achieve this by using the showPrintTools(bool) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showPrintTools(false);
</script>
{% endhighlight %}

The printing of the PDF document can be achieved in the client side by calling the print() method. 

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).print();
</script>
{% endhighlight %}

**Download Tool**

The download tool of the PDF viewer contains an option to download the PDF document. When the download button is clicked, the changes made in the PDF document will be saved in a copy of the original PDF document and it will be downloaded in the browser. The PDF viewer control provides the option to show or hide the download tool in the default toolbar. You can achieve this by using the showDownloadTool(bool) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showDownloadTool(false);
</script>
{% endhighlight %}

The PDF document can be downloaded in the client side by calling the download() method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).download();
</script>
{% endhighlight %}

**Signature tool**

The signature tool of the PDF viewer contains an option to include handwritten signatures in the PDF document. The PDF viewer control provides the option to show or hide the signature tool in the default toolbar. You can achieve this by using the showSignatureTool(bool) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showSignatureTool(false);
</script>
{% endhighlight %}

**Selection tool**

The selection tool of the PDF viewer control contains options for selection and panning interaction modes. The PDF viewer control provides the option to show or hide the selection tool in the default toolbar. You can achieve this by using the showSelectionTool(bool) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showSelectionTool(false);
</script>
{% endhighlight %}

### Text Search tool

The text search tool of the PDF viewer control is used to initiate and close the text search process in the PDF viewer control. The PDF viewer control provides the option to show or hide the text search tool in the default toolbar. You can achieve this by using the showTextSearchTool(bool) method.

{% highlight javascript %}
<script>
    $(“#pdfviewer”).data(“ejPdfViewer”).showTextSearchTool(false);
</script>
{% endhighlight %}

**APIs available for Text Search tool**

searchText(targetText)

searchText(targetText) method allows us to search the target text in the PDF document and highlights the occurrences in the pages.

{% highlight javascript %}
<script>
	$("#pdfviewer").data("ejPdfViewer").searchText("name");
</script>
{% endhighlight %}

searchNext()

The next occurrences of the searched text from the current occurrence can be searched using the searchNext() method.

{% highlight javascript %}
<script>
	$("#pdfviewer").data("ejPdfViewer").searchNext();
</script>
{% endhighlight %}

SearchPrevious()

The previous occurrence of the searched text from the current occurrence can be searched using the searchPrevious() method.

{% highlight javascript %}
<script>
	$("#pdfviewer").data("ejPdfViewer").searchPrevious();
</script>
{% endhighlight %}

matchCase(enableMatchCase)

The target text in the PDF document can be searched with its casing using the matchCase(enableMatchCase) method.

{% highlight javascript %}
<script>
	$("#pdfviewer").data("ejPdfViewer").matchCase(true);
</script>
{% endhighlight %}

cancelSearchText()

The text search can be canceled and the highlighted occurrences from the PDF viewer can be removed using the cancelSearchText() method.

{% highlight javascript %}
<script>
	$("#pdfviewer").data("ejPdfViewer").cancelSearchText();
</script>
{% endhighlight %}

**Events in the PDF viewer control**

BeforePrint

When the print option is clicked, the beforePrint event will be triggered before printing the PDF document from the PDF viewer control. We can define the event method using the BeforePrint property of the control.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" BeforePrint="beforePrint"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

<script type="text/javascript">
        function beforePrint(args) {
            alert("The PDF document is made ready for printing.");
        }
</script>
{% endhighlight %}

AfterPrint

After the printing process is completed, the afterPrint event will be triggered. We can define the event method using the AfterPrint property of the control.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" AfterPrint="afterPrint"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

<script type="text/javascript">
        function afterPrint (args) {
            alert("Printing completed successfully");
        }
</script>
{% endhighlight %}

ZoomChanged

When the zoom value of the PDF document is changed using the magnification tools, the zoomChange event will be triggered. We can define the event method using the ZoomChanged property of the control.

{% highlight javascript %}
 <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" ZoomChanged="zoomChanged"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

<script type="text/javascript">
        function zoomChanged(args) {
            alert("The magnification changes from " + args.previousZoomPercentage + " to" + args.currentZoomPercentage);
        }
</script>
 {% endhighlight %}

PageClicked

When a page of the PDF document is clicked, the pageClick event will be triggered. We can define the event method using the PageClicked property of the control.

{% highlight javascript %}
<ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="../api/PdfViewer" PageClicked="pageClicked"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>

<script type="text/javascript">
        function pageClicked (args) {
            alert("The page is clicked”);
        }
</script>
{% endhighlight %}

**Adding Custom toolbar**

The toolbar can be customized by hiding the existing toolbar. 

The following code snippet shows how to create a customer toolbar by using the client side APIs

{% highlight html %}
<body>
 <div id="toolbarDiv" style="height:38px;width:100%;border:solid black 1px" class="toolbarclass " role="toolbar">
              <div style="float:left; padding:5px;">         
                    <div class="e-pdfviewer-icon e-pdfviewer-gotoprevious" id="viewer-previous" onclick="callClientSideMethod('previous')"></div>
                    <div class="e-pdfviewer-icon e-pdfviewer-gotonext" id="viewer-next" onclick="callClientSideMethod('next')"></div>
                    <div class="e-pdfviewer-icon e-pdfviewer-zoomin" id="viewer-zoomin" onclick="callClientSideMethod('zoomin')"></div>
                    <div class="e-pdfviewer-icon e-pdfviewer-zoomout"id="viewer-zoomout" onclick="callClientSideMethod('zoomout')"></div>
                    <div class="e-pdfviewer-icon e-pdfviewer-fitwidth" id="viewer-fitwidth" onclick="callClientSideMethod('fitwidth')"></div>
                    <div class="e-pdfviewer-icon e-pdfviewer-fitpage" id="viewer-fitpage" onclick="callClientSideMethod('fitpage')"></div>                          
             </div>
            <div style="float:right; padding:5px;">
               <div class="e-pdfviewer-icon e-pdfviewer-print" id="viewer-print" onclick="callClientSideMethod('print')"></div>
                <div class="e-pdfviewer-icon e-pdfviewer-download" id="viewer-download" onclick="callClientSideMethod('download')"></div>
            </div>
        </div>
     <div>
        <div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                     <div class="control">
                        <ej:PdfViewer id="PdfViewer1" runat="server" style="width:100%" PdfService="Local" ServiceUrl="../api/PdfViewer" ></ej:PdfViewer>
                    </div>   
               </div>
        </div>
    </div>
    </div>
        <script type="text/javascript">
           $(function () {
            var pdfviewer = $("#PdfViewer1").data("ejPdfViewer");
            pdfviewer.showToolbar(false);
        });        
        function callClientSideMethod(apiName) {
             var _ejPdfViewer = $("#PdfViewer1").data("ejPdfViewer");
            switch (apiName) {
                case 'print':
                    _ejPdfViewer.print();
                    break;
                case 'zoomin':
                    _ejPdfViewer.zoomIn();
                     break;
                case 'zoomout':
                    _ejPdfViewer.zoomOut();
                    break;
                case 'fitpage':
                    _ejPdfViewer.fitToPage();
                    break;
                case 'fitwidth':
                     _ejPdfViewer.fitToWidth();
                     break;
                case 'previous':
                    _ejPdfViewer.goToPreviousPage();                    
                    break;
                case 'next':
                    _ejPdfViewer.goToNextPage();                    
                    break;
                case 'download':
                    _ejPdfViewer.download();
                    break;               
            }
        }
        </script>   
</body>
{% endhighlight %}


N> Ensure the icon images available in the referred location for the custom toolbar.

Run the sample. You can view the PDF viewer with custom toolbar.

<http://www.syncfusion.com/downloads/support/directtrac/general/ze/PdfViewerWeb_Toolbar-1881961262>