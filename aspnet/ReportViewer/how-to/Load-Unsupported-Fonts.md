---
layout: post
title: Load browser unsupported fonts
description: How to load the fonts does not supported in cross-platform browsers
platform: report-platform
documentation: ug
---

# Load unsupported fonts

In RDL, the defined fonts are not supported in cross-platform browsers. The unsupported fonts can be loaded through the **font-face** css rule in the style section of the application. 

## Using @font-face in Style Section

 * Add the &lt;style&gt; tag to headsection of the HTML page.
 * Create the CSS rule **font-face** and then add the **font-family** and **src** resources as mentioned below.
 * **font-family** -- Specifies a name that will be used as a font face value for font properties.
 * **src** -- Specifies the resource containing the font data. This can be a URL to a font file location.

 * The following code snippet describes the above steps.
 
{% highlight html %}

 <style>
     @font-face {
         font-family: Segoe UI;
         src: url(segoeui.ttf);
     }
 </style>

{% endhighlight %} 
