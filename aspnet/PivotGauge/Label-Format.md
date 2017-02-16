---
layout: post
title: Label Format | PivotGauge | ASP.NET | Syncfusion
description: label format
platform: aspnet
control: PivotGauge
documentation: ug
---

# Label Format

You can customize the format of labels displayed in the PivotGauge control using `LabelFormatSettings` property.

Following are the formats that can be applied to labels in PivotGauge:

* `NumberFormat`  - Allows the user to change the number format of the label values in PivotGauge.
* `DecimalPlaces` - Allows you to set the number of digits displayed after decimal point.
* `PrefixText`  - Allows you to add a text at the beginning of the label.
* `SuffixText` - Allows you to add text at the end of the label.

Number format for the label values can be set to any of the following type:

* Default	
* Currency
* Percentage
* Fraction
* Scientific
* Text
* Notation

{% highlight html %}

<ej:PivotGauge ID="PivotGauge1" runat="server" RowsCount="2">
 	//...
   <LabelFormatSettings NumberFormat="Percentage" DecimalPlaces="2" PrefixText="#*" SuffixText="*#" />
</ej:PivotGauge>

{% endhighlight %}

![](Label-Format_images/labelformat.png) 
