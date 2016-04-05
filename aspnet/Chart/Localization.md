---
layout: post
title: Localization| Chart  | ASP.NET Webforms | Syncfusion
description: Learn how to localize chart based on a specific culture.
platform: aspnet
control: Chart
documentation: ug
---

# Localization

EjChart supports localization for its axis labels and tooltip. To render the chart with specific culture you have to refer the corresponding **globalize** culture script and need to specify the culture name in **Locale** property of chart.   

{% highlight html %}

<!--Refer french globalize culture script-->
<script src="../scripts/cultures/globalize.culture.fr-FR.min.js"></script>

<ej:Chart ID="Chart1" runat="server" Locale="fr-FR"> 
</ej:Chart>

{% endhighlight %}

![](Localization_images/Localization_img1.png)


[Click](http://asp.syncfusion.com/demos/web/chart/localization.aspx) here to view the localization chart online demo sample.


