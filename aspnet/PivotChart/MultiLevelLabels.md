---
layout: post
title: Multi-level Labels | PivotChart | ASP.NET | Syncfusion
description: multilevellabels
platform: aspnet
control: PivotChart
documentation: ug
---

# Multi-level Labels

Multi-level labels allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expander present in the OlapChart.

{% highlight html %}

<ej:PivotChart ID="MyPivotChart1" runat="server" EnableMultiLevelLabels="true" ClientIDMode="Static">
 <%--....--%>
</ej:PivotChart>

{% endhighlight %}

## Relational

![Multi-level labels in ASP NET pivot chart with relational mode](MultiLevelLabels_images/relational.png)

## OLAP

![Multi-level labels in ASP NET pivot chart OLAP mode](MultiLevelLabels_images/olap.png)

