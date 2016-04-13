---
layout: post
title: Two Dimensional Barcodes | Barcode | ASP.NET Webforms | Syncfusion
description: two dimensional barcodes
platform: aspnet
control: Barcode
documentation: ug
---

# Two Dimensional Barcodes

## QR Barcode

A QR Barcode is a two-dimensional Barcode that consists of a grid of dark and light dots or blocks that form a square. The data encoded in the Barcode can be numeric, alphanumeric, or Shift Japanese Industrial Standards (JIS8) characters. The QR Barcode uses version from 1 to 40. Version 1 measures 21 modules x 21 modules, Version 2 measures 25 modules x 25 modules, and so on. The number of modules increases in steps of 4 modules per side up to Version 40 that measures 177 modules x 177 modules. Each version has its own capacity. By default, the Barcode control automatically set the version according to the length of the input text. The QR Barcodes are designed for industrial uses and also commonly used in consumer advertising.

Here is the code snippet to create a QR Barcode:

{% highlight html %}

<div>

<div>

<%--Sets the following properties:

Text – Text to encode

SymbologyType - Barcode Type (Default: QRBarcode)

XDimension - Size of each block (Optional, Default: 4)

--%>



<ej:Barcode ID="Barcode1" runat=server Text= "B5330E8278BC4C797C49DD3ED5AD9715"

SymbologyType="qrbarcode"

XDimension="8"></ej:Barcode>

</div>

</div>



{% endhighlight %}

## DataMatrix

DataMatrix Barcode is a two dimensional Barcode that consists of a grid of dark and light dots or blocks forming square or rectangular symbol. The data encoded in the Barcode can either be numbers or alphanumeric. They are widely used in printed media such as labels and letters. You can read it easily with the help of a Barcode reader and mobile phones.

