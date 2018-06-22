---
layout: post
title: Supported and unsupported elements of Syncfusion Essential ASP .NET PDF viewer.
description: Supported and unsupported elements of Syncfusion Essential ASP .NET PDF viewer.
platform: aspnet
control: PDF viewer
documentation: ug
keywords: PDF viewer, pdfviewer
---

## Supported and Unsupported Elements

The supported and un-supported elements of the PDF viewer control are:

<table>
<tr>
<td>
{{'**Features**'| markdownify }}
</td>
<td>
{{'**Support**'| markdownify }}
</td>
</tr>
<tr>
<td>
Text
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Graphical Elements(lines, curves etc.,)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Fonts**'| markdownify }}
</td>
</tr>
<tr>
<td>
Standard Fonts
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
TrueType Fonts***
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Embedded Fonts(Type 0, Type 1,Type 3)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Image Formats**'| markdownify }}
</td>
</tr>
<tr>
<td>
JPEG
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
PNG
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
TIFF
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Inline images
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Image masking Techniques**'| markdownify }}
</td>
</tr>
<tr>
<td>
Soft Mask
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Image Mask
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Color space**'| markdownify }}
</td>
</tr>
<tr>
<td>
RGB
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
CMYK
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Gray
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
ICC
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Indexed
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
CalRGB*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
CalGray*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Lab*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Separation*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
DeviceN*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Pattern*
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Compression Filters**'| markdownify }}
</td>
</tr>
<tr>
<td>
DCTDecode (Image, Content)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
CCITTFaxDecode (Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
FlateDecode (Image, Content)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
LZWDecode (Content,Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
ASCII85Decode (Content, Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
ASCIIHexDecode (Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
JBIG2Decode (Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
RunLengthDecode(Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
JPXDecode(Image)
</td>
<td>
Yes
</td>
</tr>
<tr>
<td colspan="2" rowspan="1">
{{'**Interactive Features** '| markdownify }}
</td>
</tr>
<tr>
<td>
Actions
</td>
<td>
No
</td>
</tr>
<tr>
<td>
Annotations**
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Hyperlink
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Attachments
</td>
<td>
No
</td>
</tr>
<tr>
<td>
Bookmarks
</td>
<td>
No
</td>
</tr>
<tr>
<td>
Form
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Page Navigation 
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Zoom
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Selection
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Search
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Encrypted Documents
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Edit
</td>
<td>
No
</td>
</tr>
<tr>
<td>
Conformance
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Print
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Download
</td>
<td>
Yes
</td>
</tr>
<tr>
<td>
Export to image
</td>
<td>
No
</td>
</tr>
</table>

Supported only for shapes and text*

Supports only text markup annotations**

When the document contains text that uses TrueType System Fonts to be rendered, the content in the PDF document is rendered using the font installed in the system or machine in the PDF Viewer control. If the required font is not installed in the system, the contents would be rendered using **Arial** font.***