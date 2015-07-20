---
layout: post
title: Qualitative-Range
description: qualitative range
platform: aspnet
control: BulletGraph	
documentation: ug
---

# Qualitative Range

Qualitative Range represents the quality of a specific range in quantitative scale like good, bad and satisfactory. Color for each qualitative range is customized using RangeStroke property. The RangeEnd property specifies the ending point of the qualitative range. Minimum value of quantitative scale is considered as the starting point of first qualitative range and previous end points are considered as starting point for other qualitative ranges. 
{% highlight html %}
[ASP.NET]



&lt;ej:BulletGraph ID="BulletGraph1" QualitativeRangeSize="60" Value="8" ComparativeMeasureValue="5" Width="600px" Height="120px" runat="server"&gt;                        

            &lt;QualitativeRanges&gt;

                &lt;ej:QualitativeRanges RangeEnd="35" RangeStroke="darkred" RangeOpacity="0.5"&gt;&lt;/ej:QualitativeRanges&gt;

                &lt;ej:QualitativeRanges RangeEnd="50" RangeStroke="red" RangeOpacity="1"&gt;&lt;/ej:QualitativeRanges&gt;

                &lt;ej:QualitativeRanges RangeEnd="75" RangeStroke="blue" RangeOpacity="0.7"&gt;&lt;/ej:QualitativeRanges&gt;

                &lt;ej:QualitativeRanges RangeEnd="90" RangeStroke="lightgreen" RangeOpacity="1"&gt;&lt;/ej:QualitativeRanges&gt;

                &lt;ej:QualitativeRanges RangeEnd="100" RangeStroke="green" RangeOpacity="1"&gt;&lt;/ej:QualitativeRanges&gt;

            &lt;/QualitativeRanges&gt;



            &lt;QuantitativeScaleSettings Minimum="0" Maximum="100" Interval="10"&gt;

                &lt;Location X="50" Y="20" /&gt;

                &lt;FeatureMeasures&gt;

                    &lt;ej:FeatureMeasures Category="Year 1" ComparativeMeasure="75" Value="55" /&gt;

                    &lt;ej:FeatureMeasures Category="Year 2" ComparativeMeasure="70" Value="65" /&gt;

                    &lt;ej:FeatureMeasures Category="Year 3" ComparativeMeasure="65" Value="80" /&gt;

                &lt;/FeatureMeasures&gt;

            &lt;/QuantitativeScaleSettings&gt;

        &lt;/ej:BulletGraph&gt;

{% endhighlight  %}

The following screenshot displays Bullet Graph with different qualitative ranges in different colors. In this image, range 0 to 35 represents bad performance, 35 to 50 represents average performance, 50 to 75 represents that the performance is above average, 75 to 90 represents good performance and above 90 represents excellent performance.

![](Qualitative-Range_images/Qualitative-Range_img1.png)
{:.image }


