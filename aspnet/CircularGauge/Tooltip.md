---
layout: post
title: Tooltip | CircularGauge | ASP.NET Webforms | Syncfusion
description: tooltip
platform: aspnet
control: Circular Gauge
documentation: ug
---

# Tooltip

* Tooltip feature has been added to the Circular Gauge. Circular Gauge has several elements such as pointers, label, customLabel, scales, etc.  
* There is a need for Tooltip feature in the Circular Gauge control because whenever the text hides or overrides with other gauge elements, it may not be fully visible. For resolving those problems Tooltip feature has been implemented in the Circular Gauge control.

## Default Tooltip

* `Tooltip` has three attributes in it. The first two attributes such as `ShowLabelTooltip` and `ShowCustomLabelTooltip` are for enabling the Tooltip for label as well as custom label in default appearance. 
* `ShowLabelTooltip` is to enable the Tooltip for labels and `ShowCustomLabelTooltip` is for enabling the Tooltip option for customLabels.


  {% highlight html %}

        <ej:circulargauge runat=”server” id=”circularGaugeTooltip” backgroundcolor=”transparent” enableAnimation=”false”>



        <%-- Defines the tooltip object-- %>

        <Tooltip ShowCustomLabelTooltip=”true” ShowLabelTooltip=”true” />



        <%-- Customizes the scale options-- %>

        <Scales>

        <ej:CircularScales ShowLabels=”true” Radius="130" >



        <PointerCollection>

        <ej:Pointers Value=”60” Length=”95” >

        </ej:Pointers>

        </PointerCollection>



        <%-- Customizes the custom label options-- %>

        <CustomLabelCollection>

        <ej:CircularCustomLabel Value=”0 9 5 3 4 5”>

        <Font FontFamily ="Arial" FontStyle="Bold" Size="20px" />

        <Position X ="180" Y="200" />

        </ej:CircularCustomLabel>

        </CustomLabelCollection>

        </ej:CircularScales>

        </Scales>

        </ej:circulargauge>

{% endhighlight %}

Execute the above code to render the following output.

 ![](Tooltip_images/Tooltip_img1.png)





## Tooltip Template

In Tooltip option, you can customize the Tooltip window by adding the tooltip template on that page with the help of API `TemplateID`. Refer to the following code example to know more about Tooltip template.


{% highlight html %}



<ej:circulargauge runat=”server” id=”circularGaugeTooltip” backgroundcolor=”transparent” nableAnimation=”false”>



<%-- Defines the tooltip object-- %>

<Tooltip>



<%-- Enables the custom label tooltip-- %>

ShowCustomLabelTooltip=”true”



<%-- Enables the label tooltip-- %>

ShowLabelTooltip=”true”



<%-- Enables the Tooltip Template-- %>

TemplateID=”Tooltip”/>



<%-- Customizes the scale options-- %>

<Scales>

<ej:CircularScales ShowLabels=”true” Radius="130" >



<%-- Customizes the pointers options-- %>

<PointerCollection>

<ej:Pointers Value=”60” Length=”95” >

</ej:Pointers>

</PointerCollection>



<%-- Customizes the custom label options-- %>

<CustomLabelCollection>

<ej:CircularCustomLabel Value=”0 9 5 3 4 5”>

<Font FontFamily ="Arial" FontStyle="Bold" Size="20px" />

<Position X ="180" Y="200" />

</ej:CircularCustomLabel>

</CustomLabelCollection>

</ej:CircularScales>

</Scales>

</ej:circulargauge>

{% endhighlight %}
Execute the above code to render the following output.


 ![](Tooltip_images/Tooltip_img2.png)








