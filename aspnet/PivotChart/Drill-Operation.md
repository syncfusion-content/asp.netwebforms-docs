---
layout: post
title: Drill Operation | PivotChart | ASP.NET | Syncfusion
description: drill operation
platform: aspnet
control: PivotChart
documentation: ug
---

# Drill Operation

This is a basic feature of PivotChart through which the amount of information can be limited, for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the Context Menu present in the PivotChart.

Drill up, also called roll up, navigates from more detailed data to less detailed data, by climbing up a concept hierarchy for a dimension.

Drill down, also called roll down, is the reverse of drill up. It navigates from less detailed data to more detailed data, by climbing down a concept hierarchy for a dimension.

![](Drill-Operation_images/Drill-Operation_img1.png)


![](Drill-Operation_images/Drill-Operation_img2.png)


DrillSuccess event gets triggered when you right-click on the PivotChart and select any option available from the context menu to perform drill up or drill down operation.

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