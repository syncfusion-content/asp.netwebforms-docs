---
layout: post
title:  GrandTotal Hiding | PivotGrid | ASP.NET | Syncfusion
description: GrandTotal Hiding
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grand total hiding

Grand total hiding can be classified into three categories as follows:

* Row grand total hiding
* Column grand total hiding
* Both

## Row grand total hiding

You can hide the **Grand Total** in row alone by setting the `EnableRowGrandTotal` property to `false`.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableRowGrandTotal="false">
    <%--...--%>
</ej:PivotGrid>

{% endhighlight %}

![Hiding row totals in ASP NET pivot grid control](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column grand total hiding

You can hide the **Grand Total** in column alone by setting the `EnableColumnGrandTotal` property to `false`.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableColumnGrandTotal="false">
   <%--...--%>
</ej:PivotGrid>

{% endhighlight %}

![Hiding column totals in ASP NET pivot grid control](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the `EnableGrandTotal` property to `false`.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGrandTotal="false">
    <%--...--%>
</ej:PivotGrid>

{% endhighlight %}

![Hiding totals in ASP NET pivot grid control](GrandTotal-Hiding_images/enableGrandTotal.png)