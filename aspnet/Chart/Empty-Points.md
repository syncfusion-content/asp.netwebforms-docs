---
layout: post
title: Empty-Points
description: empty points
platform: aspnet
control: Chart
documentation: ug
---

# Empty Points

The data that is passed to the Chart can have null or undefined values that are considered as empty points. Series type like line, spline, area, splinearea, stepline, steparea, column, bar, bubble, scatter, hilo, hiloopenclose, candle, rangecolumn and stacking series having empty point support.


{% highlight html %}
[ASP.NET] 

  &lt;ej:Chart ID="Chart1" runat="server"&gt;       

         &lt;Series&gt;

            &lt;ej:Series Name="Course" Type="Column"&gt;



                &lt;Points&gt;

                       &lt;ej:Points X="1" Y="210" /&gt;

                    &lt;ej:Points X="2" Y="150" /&gt;

                    &lt;ej:Points X="3" Y="200" /&gt;

                    &lt;ej:Points X="4" Y="23" IsEmpty="true"/&gt;

                    &lt;ej:Points X="5" Y="170" /&gt;

                    &lt;ej:Points X="6" Y="230" /&gt;

                    &lt;ej:Points X="7" Y="1200" /&gt;

                    &lt;/Points&gt;

            &lt;/ej:Series&gt;

        &lt;/Series&gt;  

  &lt;/ej:Chart&gt;


{% endhighlight %}
![](Empty-Points_images/Empty-Points_img1.png)
{:.image }


