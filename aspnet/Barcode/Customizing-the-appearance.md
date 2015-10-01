---
layout: post
title: Customizing the appearance | Barcode | ASP.NET Webforms | Syncfusion
description: customizing the appearance
platform: aspnet
control: Barcode
documentation: ug
---

# Customizing the appearance

A page or printed media with Barcode often appears colorful in the background and surrounding region with other contents. In such cases the Barcode can also be customized to suit the needs. You can achieve this by changing the darkBarColor property.



N> This color customization is possible only for one dimensional barcodes and it is not supported for two dimensional barcodes.



{% highlight html %}

<div>

    <div>

<ej:Barcode ID="Barcode1"  runat=server Text= "B5330E8278BC4C797C49DD3ED5AD9715" SymbologyType="Code39" DarkBarColor="blue"></ej:Barcode>

    </div>

</div>
</code>
</pre>


{% endhighlight %}



Execute the above code to render the following output.



![](Customizing-the-appearance_images/Customizing-the-appearance_img2.png) 

The height of the barcode can be changed using the BarHeight property. The equivalent property to change the block size for two dimensional barcode is XDimension.



{% highlight html %}

<div>

    <div>

<ej:Barcode ID="Barcode1"  runat=server Text="B5330E8278BC4C797C49DD3ED5AD9715" SymbologyType="Code39" DarkBarColor="#990099" BarHeight="45" DisplayText="false"></ej:Barcode>

    </div>

</div>


{% endhighlight %}



Execute the above code to render the following output.


![](Customizing-the-appearance_images/Customizing-the-appearance_img3.png) 


