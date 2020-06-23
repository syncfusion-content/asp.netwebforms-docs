---
layout: post
title: Data Label | SunburstChart | ASP.NET Webforms | Syncfusion
description: Learn about data label support in Syncfusion ASP.NET Webforms SunburstChart control and more details.
platform: aspnet
control: SunburstChart
documentation: ug
---

# Data Labels 

Sunburst data labels are used to display the data related to the segment. It helps to provide the information about the data points to the users.
You can enable or disable the data labels by setting the **visible** property of the DataLabelSettings to true as shown in the below code

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true"></DataLabelSettings>                             
</ej:SunburstChart> 

 {% endhighlight %}

![](DataLabel_images/DataLabel_img1.png)

## Label Overflow mode

When you represent huge data with data labels, they may intersect each other. You can avoid this using the *SunburstLabelOverflowMode* property.

The following properties are used to avoid the overlapping.
*	Trim – To trim the large data labels.
*	Hide – To hide the overlapped data labels.
The following code shows how to set Hide and Trim mode.

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true" SunburstLabelOverflowMode="hide"></DataLabelSettings>                             
</ej:SunburstChart> 

 {% endhighlight %}

![](DataLabel_images/DataLabel_img2.png) 

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true" SunburstLabelOverflowMode="trim"></DataLabelSettings>                             
</ej:SunburstChart> 

 {% endhighlight %}

![](DataLabel_images/DataLabel_img3.png)

## Label Rotation Mode
You can rotate the data label by using *SunburstLabelRotationMode* property. By default, the SunburstLabelRotationMode is set as **angle**. 

The following code shows how to set SunburstLabelRotationMode as normal and angle.

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true" SunburstLabelRotationMode="normal"></DataLabelSettings>                             
</ej:SunburstChart> 

 {% endhighlight %}

![](DataLabel_images/DataLabel_img4.png)

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true" SunburstLabelRotationMode="angle"></DataLabelSettings>                             
</ej:SunburstChart> 

{% endhighlight %}

![](DataLabel_images/DataLabel_img5.png)
 
## Customizing the data labels
You can customize the appearance of the data point using the `Font` property.


{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<DataLabelSettings Visible="true" SunburstLabelRotationMode="angle">
<Font Color="Black" Font-Weight="bold" Size="15px"></Font>
</DataLabelSettings>                             
</ej:SunburstChart> 

{% endhighlight %}

![](DataLabel_images/DataLabel_img6.png)
