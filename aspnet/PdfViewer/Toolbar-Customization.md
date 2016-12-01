---
layout: post
title: Toolbar customization of Syncfusion Essential ASP.NET PDF viewer.
description: Toolbar customization of Syncfusion Essential ASP.NET PDF viewer.
platform: ASP.NET
control: PDF viewer
documentation: ug
keywords: pdfviewer, PDF viewer
---

## Toolbar Customization

**Customizing default toolbar**

The default toolbar is grouped into the following set of tools.
<table>
<tr>
<td>
{{'**MagnificationTools**'| markdownify }}
</td>
<td>
Contains ZoomIn, ZoomOut, Zoom, FitPage and FitWidth tools
</td>
</tr>
<tr>
<td>
{{'**NavigationTools**'| markdownify }}
</td>
<td>
Contains GoToFirst, GoToLast, GoToNext and GoToLast tools
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
Contains download tool
</td>
</tr>
<tr>
<td>
{{'**SearchTool**'| markdownify }}
</td>
<td>
Contains text search tool
</td>
</tr>
</table>

The PDF viewer has an option to show or hide these grouped items in the default toolbar.  You can hide/display any of these tools by using the toolbarSettings property.

**Adding Custom toolbar**

The toolbar can be customized as required, by hiding the existing toolbar.

The below code snippet shows how to create a customer toolbar by using the client side APIs.

{% highlight html %}
<body>
  <div id="container" onmousemove="mousemovefunction(event)" style="width: 100%; height: 680px;"></div>
        <div id="toolbarDiv" style="height:38px;width:100%;border:solid black 1px" class="toolbarclass " role="toolbar">
              <div style="float:left; padding:5px;">         
                    <div class="e-pdfviewer-customtoolbar-previous" id="viewer-previous" onclick="callClientSideMethod('previous')"></div>
                    <div class="e-pdfviewer-customtoolbar-next" id="viewer-next" onclick="callClientSideMethod('next')"></div>
                    <input id="currentPage" class="e-pdfviewer-pagenumber e-pdfviewer-elementalignments" type="text" onkeypress="updatePageNumber(event)"/>
                    <span id="totalPageCount" class="e-pdfviewer-labelpageno">  </span>
                    <div class="e-pdfviewer-customtoolbar-zoomin" id="viewer-zoomin" onclick="callClientSideMethod('zoomin')"></div>
                    <div class="e-pdfviewer-customtoolbar-zoomout"id="viewer-zoomout" onclick="callClientSideMethod('zoomout')"></div>
                    <div class="e-pdfviewer-customtoolbar-fitwidth" id="viewer-fitwidth" onclick="callClientSideMethod('fitwidth')"></div>
                    <div class="e-pdfviewer-customtoolbar-fitpage" id="viewer-fitpage" onclick="callClientSideMethod('fitpage')"></div>                          
             </div>
            <div style="float:right; padding:5px;">
                <div class="e-pdfviewer-customtoolbar-print" id="viewer-print" onclick="callClientSideMethod('print')"></div>
                <div class="e-pdfviewer-customtoolbar-download" id="viewer-download" onclick="callClientSideMethod('download')"></div>
            </div>
        </div>
    <div>
        <div class="content-container-fluid">
            <div class="row">
                <div class="cols-sample-area">
                    <div class="control">
                        <ej:PdfViewer id="PdfViewer1" runat="server" style="width:100%" PdfService="Local" ServiceUrl="../api/PdfViewer"  PageChanged="pageChange" DocumentLoaded="onDocumentLoad"></ej:PdfViewer>
                    </div>
                </div>
            </div>
         </div>
    </div>
        <script type="text/javascript">
           var currentPageNumber = 1;
        $(function () {
            var pdfviewer = $("#PdfViewer1").data("ejPdfViewer");
            document.getElementById('currentPage').value = 1;
            document.getElementById('totalPageCount').innerHTML = "/" +pdfviewer.pageCount;            
            pdfviewer.showToolbar(false);
        });
        function onDocumentLoad() {
            var _ejPdfViewer = $("#PdfViewer1").data("ejPdfViewer");
            document.getElementById('totalPageCount').innerHTML = "/" + _ejPdfViewer.pageCount;
        }
        function pageChange(args) {        
            currentPageNumber = args.currentPageNumber;
            document.getElementById('currentPage').value = args.currentPageNumber;        
        }
         function updatePageNumber(event){
            var _ejPdfViewer = $("#PdfViewer1").data("ejPdfViewer");
            currentPageNumber = document.getElementById('currentPage').value;
            if (event.which == 13) {
                if (currentPageNumber > 0 && currentPageNumber <= _ejPdfViewer.pageCount) {
                    _ejPdfViewer.goToPage(currentPageNumber);
                } else {
                    currentPageNumber = _ejPdfViewer.currentPageNumber;
                }
            }
        }
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
        <style>     
    .e-pdfviewer-customtoolbar-zoomin:before{
      content: url('../images/pdfviewer/CustomToolbarImages/zoomin.png');
          }
    .e-pdfviewer-customtoolbar-zoomout:before{
      content: url('../images/pdfviewer/CustomToolbarImages/zoomout.png');
        }
    .e-pdfviewer-customtoolbar-previous:before{
        content: url('../images/pdfviewer/CustomToolbarImages/previous.png');
        }
    .e-pdfviewer-customtoolbar-next:before{
        content: url('../images/pdfviewer/CustomToolbarImages/next.png');
        }
    .e-pdfviewer-customtoolbar-fitwidth:before{
        content: url('../images/pdfviewer/CustomToolbarImages/fitwidth.png');
        }
    .e-pdfviewer-customtoolbar-print:before{
        content: url('../images/pdfviewer/CustomToolbarImages/print.png');
        }
    .e-pdfviewer-customtoolbar-download:before{
        content: url('../images/pdfviewer/CustomToolbarImages/download.png');
        }

    .e-pdfviewer-customtoolbar-fitpage:before{
        content: url('../images/pdfviewer/CustomToolbarImages/fitpage.png');
        }
    </style>
</body>
{% endhighlight %}


N> Ensure the icon images available in the referred location for the custom toolbar.

Run the sample. You can view the PDF viewer with custom toolbar.
