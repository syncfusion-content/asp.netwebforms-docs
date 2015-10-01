---
layout: post
title: Barcode types and supported characters | Barcode | ASP.NET Webforms | Syncfusion
description: barcode types and supported characters
platform: aspnet
control: Barcode
documentation: ug
---

# Barcode types and supported characters

The following table contains the supported types and associated valid characters.

Table of Barcode types and supported character

<table>
<tr>
<th>
Symbol</th><th>
Enum Value</th><th>
Supported characters</th><th>
Length</th></tr>
<tr>
<td>
QR Barcode</td><td>
QRBarcode</td><td>
0,1,2,3,4,5,6,7,8,90–9, A–Z (upper-case only), space, $, %, *, +, -,., /, :Shift JIS characters</td><td>
variable</td></tr>
<tr>
<td>
DataMatrix</td><td>
DataMatrix</td><td>
All ASCII characters</td><td>
</td></tr>
<tr>
<td>
Code 39</td><td>
Code39</td><td>
0-9, A-Z,a dash(-),a dot(.),$,/,+,%, SPACE</td><td>
variable</td></tr>
<tr>
<td>
Code 39 Extended</td><td>
Code39Extended</td><td>
0-9 A-Z a-z</td><td>
variable</td></tr>
<tr>
<td>
Code 11</td><td>
Code11</td><td>
0-9, a dash(-)</td><td>
variable</td></tr>
<tr>
<td>
Codabar</td><td>
Codabar</td><td>
0-9,-,$,:,/,a dot(.),+</td><td>
variable</td></tr>
<tr>
<td>
Code 32</td><td>
Code32</td><td>
0 1 2 3 4 5 6 7 8 9Text length should be 8</td><td>
8</td></tr>
<tr>
<td>
Code 93</td><td>
Code93</td><td>
1 2 3 4 5 6 7 8 9 0 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z - . $ / + % SPACE</td><td>
variable</td></tr>
<tr>
<td>
Code 93 Extended</td><td>
Code93Extended</td><td>
All 128 ASCII characters</td><td>
variable</td></tr>
<tr>
<td>
Code 128 A</td><td>
Code128A</td><td>
NUL (0x00) SOH (0x01) STX (0x02) ETX (0x03) EOT(0x04) ENQ (0x05) ACK (0x06) BEL (0x07) BS (0x08) HT (0x09) LF (0x0A) VT(0x0B) FF (0x0C) CR (0x0D) SO (0x0E) SI (0x0F) DLE (0x10) DC1 (0x11) DC2(0x12) DC3 (0x13) DC4 (0x14) NAK (0x15) SYN (0x16) ETB (0x17) CAN(0x18) EM (0x19) SUB (0x1A) ESC (0x1B) FS (0x1C) GS (0x1D) RS (0x1E) US(0x1F) SPACE (0x20) " ! # $ % & ' ( ) * + , - . / 0 1 2 3 4 5 6 7 8 9 : ; &lt; = &gt; ? @ AB C D E F G H I J K L M N O P Q R S T U V W X Y Z [ / ]^ _</td><td>
variable</td></tr>
<tr>
<td>
Code 128 B</td><td>
Code128B</td><td>
SPACE (0x20) ! " # $ % & ' ( ) * + , - . / 0 1 2 3 4 5 6 7 8 9 :; &lt; = &gt; ? @ A B C D E F G H I J K L M N O P Q R S T U V W X Y Z [ / ]^ _ ` ab c d e f g h i j k l m n o p q r s t u v w x y z { | } ~ DEL (•)</td><td>
variable</td></tr>
<tr>
<td>
Code 128 C</td><td>
Code128C</td><td>
0 1 2 3 4 5 6 7 8 9</td><td>
variable</td></tr>
</table>


