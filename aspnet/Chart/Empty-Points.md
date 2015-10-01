---
layout: post
title: Empty Points | Chart | ASP.NET Webforms | Syncfusion
description: empty points
platform: aspnet
control: Chart
documentation: ug
---

# Empty Points

The data that is passed to the Chart can have null or undefined values that are considered as empty points. Series type like line, spline, area, splinearea, stepline, steparea, column, bar, bubble, scatter, hilo, hiloopenclose, candle, rangecolumn and stacking series having empty point support.


{% highlight html %}


  <ej:Chart ID="Chart1" runat="server">       

         <Series>

            <ej:Series Name="Course" Type="Column">



                <Points>

                       <ej:Points X="1" Y="210" />

                    <ej:Points X="2" Y="150" />

                    <ej:Points X="3" Y="200" />

                    <ej:Points X="4" Y="23" IsEmpty="true"/>

                    <ej:Points X="5" Y="170" />

                    <ej:Points X="6" Y="230" />

                    <ej:Points X="7" Y="1200" />

                    </Points>

            </ej:Series>

        </Series>  

  </ej:Chart>


{% endhighlight %}
![](Empty-Points_images/Empty-Points_img1.png)



