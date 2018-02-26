---
layout: post
title: Altering apperance of Syncfusion Essential ASP.NET PDF viewer.
description: Altering apperance of Syncfusion Essential ASP.NET PDF viewer.
platform: ASP.NET
control: PDF viewer
documentation: ug
---

## Appearance

You can apply themes to the PDF viewer to match the themes of your application.

Following are the built-in themes available in PDF viewer.

* flat-azure
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap
* high-contrast-01
* high-contrast-02
* material
* office-365

By default, ‘flat-azure’ theme is applied to PDF viewer. You can change the theme by changing the stylesheet reference. You can apply ‘gradient-saffron’ theme to ejPdfViewer by using the stylesheet reference as follows

{% highlight javascript %}
<script src="assets/external/jquery-1.11.3.min.js" type="text/javascript"></script>
<script src="assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script>
<script src="assets/scripts/web/ej.web.all.min.js" type="text/javascript"></script>
<!—style sheet for ‘gradient-saffron’ theme.-->
<link href="assets/css/web/gradient-saffron/ej.widgets.all.min.css" rel="stylesheet" type="text/css" />
{% endhighlight %}

The following screenshot shows the PDF viewer in ‘gradient-saffron’ theme.

![](Appearance_images/Appearance_img1.png)

