---
layout: post
title:  GrandTotal Hiding | PivotGrid | ASP.NET | Syncfusion 
description: GrandTotal Hiding
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grand Total Hiding

Grand Total Hiding can be classified into three categories.

* Row Grand Total Hiding
* Column Grand Total Hiding
* Both

## Row Grand Total Hiding

You can hide the **Grand Total** in row alone by setting the property `EnableRowGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableRowGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column Grand Total Hiding

You can hide the **Grand Total** in column alone by setting the property `EnableColumnGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableColumnGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the property `EnableGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableGrandTotal.png)