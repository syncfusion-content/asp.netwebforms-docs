---
layout: post
title:  Summary Customization | PivotGrid | ASP.NET | Syncfusion 
description: Summary Customization
platform: aspnet
control: PivotGrid
documentation: ug
---

# Summary Customization

Allows you to show or hide the PivotGrid totals in column and row sections. Summary customization can been classified into two different categories.

* Sub Total Customization
* Grand Total Customization


## Sub Total Customization

You can hide the **Sub Total** for respective fields in rows and columns by setting the property `ShowSubTotal` to `false`

## Client Mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
        //...
        <Columns>
            <ej:Field FieldName="[Date].[Fiscal]"></ej:Field>
            <ej:Field ShowSubTotal="false"></ej:Field>
        </Columns>
    </DataSource>
</ej:PivotGrid>

{% endhighlight %}


## Server Mode

{% highlight c# %}

private PivotReport BindDefaultData()
{
    PivotReport pivotSetting = new PivotReport();
    pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Date", FieldHeader = "Date", TotalHeader = "Total", ShowSubTotal = false });
    pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total", ShowSubTotal = true });
    pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total", ShowSubTotal = false });
    pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
    return pivotSetting;
}

{% endhighlight %}

![](Summary-Customization_images/SubTotal.png)


## Grand Total Customization

Grand Total Customization can be classified into three categories.

* Row Grand Total Customization
* Column Grand Total Customization
* Both

## Row Grand Total Customization

You can hide the **Grand Total** in row alone by setting the property `EnableRowGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableRowGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](Summary-Customization_images/enableRowGrandTotal.png)

## Column Grand Total Customization

You can hide the **Grand Total** in column alone by setting the property `EnableColumnGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableColumnGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](Summary-Customization_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the property `EnableGrandTotal` to `false`

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGrandTotal=”false”>
    //...
</ej:PivotGrid>

{% endhighlight %}

![](Summary-Customization_images/enableGrandTotal.png)