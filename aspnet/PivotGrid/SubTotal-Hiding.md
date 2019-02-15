---
layout: post
title:  SubTotal Hiding | PivotGrid | ASP.NET | Syncfusion
description: SubTotal Hiding
platform: aspnet
control: PivotGrid
documentation: ug
---

# Sub total hiding

N> This feature is applicable only for the relational data source.

You can hide the **Sub Total** for respective fields in rows and columns by setting the `ShowSubTotal` property to `false`.

## Client mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <DataSource>
    <Rows>
        <ej:Field FieldName="Date" FieldCaption="Date" ShowSubTotal="False" >
        </ej:Field>
        <ej:Field FieldName="Country" FieldCaption="Country">
        </ej:Field>
    </Rows>
    <Columns>
        <ej:Field FieldName="Product" FieldCaption="Product">
        </ej:Field>
    </Columns>
    <Values>
        <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
    </Values>
    </DataSource>
</ej:PivotGrid>

{% endhighlight %}


## Server mode

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

![SubTotal hiding support in ASP NET pivot grid control](SubTotal-Hiding_images/SubTotal.png)

