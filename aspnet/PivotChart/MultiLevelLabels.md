---
layout: post
title: Multi-level Labels
description: multilevellabels
platform: aspnet
control: PivotChart
documentation: ug
---

# Multi-level Labels

Multi-level labels allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expander present in the OlapChart.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" EnableMultiLevelLabels="true" ClientIDMode="Static">
 //..
</ej:PivotChart>

{% endhighlight %}   

## Relational

![](MultiLevelLabels_images/relational.png)

## OLAP

![](MultiLevelLabels_images/olap.png)

