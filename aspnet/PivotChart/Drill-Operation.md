---
layout: post
title: Drill Operation | PivotChart | ASP.NET | Syncfusion
description: This document illustrates drill operation with respective to the modes of ASP.NET PivotChart control
platform: aspnet
control: PivotChart
documentation: ug
---

# Drill operation

This is a basic feature of the pivot chart through which the amount of information can be limited for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the context menu present in the pivot chart.

Drill up, also called roll up, navigates from the inner most level (having detailed information about member) to any other outer levels by climbing up a concept hierarchy for a dimension.

Drill down, also called roll down, is the reverse of drill up. It navigates from the outer level to inner most level by climbing down the concept hierarchy for the dimension.

![Drill-down option of ASP NET pivot chart control](Drill-Operation_images/Drill-Operation_img1.png)


![Drill-up option of ASP NET pivot chart control](Drill-Operation_images/Drill-Operation_img2.png)


The "DrillSuccess" event is triggered when you right-click the pivot chart and select any option available from the context menu to perform drill up or drill down operation.

{% tabs %}

{% highlight html %}
<ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc">;
    <ClientSideEvents DrillSuccess="DrillSuccess" />
    <Size Width="950px" Height="460px"></Size>
</ej:PivotChart>
{% endhighlight %}

{% highlight js %}
<script type="text/javascript">

    function DrillSuccess(args) {

        alert("Drill Success");

    }

</script>
{% endhighlight %}

{% endtabs %}