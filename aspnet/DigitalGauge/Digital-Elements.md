---
layout: post
title: Digital Elements | DigitalGauge | ASP.NET Webforms | Syncfusion
description: digital elements
platform: aspnet
control: Digital Gauge
documentation: ug
---

# Digital Elements

## Text Customization

* The attribute value refers the text displayed in the Digital Gauge. This text is applicable only for that item instead of all items. Text color is changed by using the property textColor.
* It is possible to align the text inside the Digital Gauge control by using the property textAlign. Two possible values for text align are as follows
  
  a. left
  
  b. right



{% highlight html %}

<ej:DigitalGauge runat="server" ID="DigitalGauge1">



            <Items>

            <%-- Adding Text properties --%>

            <ej:DigitalGaugeItems TextAlign="Right" Value="STOP">



            </ej:DigitalGaugeItems>



            </Items>

            </ej:DigitalGauge>

{% endhighlight %}

Execute the above code examples to render the DigitalGauge as follows.

![](Digital-Elements_images/Digital-Elements_img1.png)

Digital Gauge control with text customization
{:.caption} 