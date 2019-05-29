---
layout: post
title: Number format  | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to define number formats and its types in ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Number format

Allows you to specify the required number format which is to be used in values of the pivot grid by setting the `format` option. Following are the supported number formats:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction
* string

## Relational

### Client mode

{% highlight js %}

<ej:PivotGrid ID="PivotGrid1" Url="" runat="server" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            <ej:Field FieldName="State" FieldCaption="State"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
        </Columns>
        <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount" Format="currency"></ej:Field>
            <ej:Field FieldName="Quantity" FieldCaption="Quantity" Format="decimal"></ej:Field>
        </Values>
    </DataSource>
    <ClientSideEvents Load="onLoad" />

</ej:PivotGrid>

<script type="text/javascript">
        function onLoad(args) {
            args.model.dataSource.data = pivot_dataset; // Datasource
        }
</script>

{% endhighlight %}

![Number formatting in ASP NET pivot grid relational client mode](Number-Format_images/RelationalClient.png)

### Server mode

 You can set the number format through the `Format` property. You should specify the format to the property as per the MS standard notation.

{% highlight C# %}

private PivotReport BindDefaultData()
    {

        PivotReport pivotSetting = new PivotReport();
        pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
        pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
        //specify the format here
        pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "E", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
        return pivotSetting;
    }

{% endhighlight %}

![Number formatting in ASP NET pivot grid relational server mode](Number-Format_images/RelationalServer.png)

## OLAP

### Client mode

{% highlight js %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="https://bi.syncfusion.com/olap/msmdpump.dll">
      <Rows>
        <ej:Field FieldName="[Customer].[Customer Geography]"></ej:Field>
      </Rows>
      <Columns>
       <ej:Field FieldName="[Product].[Product Categories]"></ej:Field>
      </Columns>
      <Values>
       <ej:Field Axis="Column">
      <Measures>
       <ej:MeasuresItems FieldName="[Measures].[Internet Sales Amount]" Format="percent" />
      </Measures>
     </ej:Field>
    </Values>
</DataSource>
</ej:PivotGrid>

<script type="text/javascript">
       //...
</script>

{% endhighlight %}

![Number formatting in ASP NET pivot grid OLAP client mode](Number-Format_images/OlapClient.png)

### Server mode

 The OLAP server mode supports the following number formats in addition to the above mentioned formats:
* General
* RoundTrip
* FixedPoint
* HexaDecimal

N> You can set the number format through the `Format` property.

{% highlight C# %}

private OlapReport CreateOlapReport()
{
     OlapReport olapReport = new OlapReport();
     olapReport.CurrentCubeName = "Adventure Works";

     MeasureElements measureElement = new MeasureElements();
     measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Internet Sales Amount]", Format = NumberFormat.FixedPoint }); //Specify the format here

     DimensionElement dimensionElementRow = new DimensionElement();
     dimensionElementRow.Name = "Date";
     dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

     DimensionElement dimensionElementColumn = new DimensionElement();
     dimensionElementColumn.Name = "Customer";
     dimensionElementColumn.AddLevel("Customer Geography", "Country");

     olapReport.SeriesElements.Add(dimensionElementRow);
     olapReport.CategoricalElements.Add(dimensionElementColumn);
     olapReport.CategoricalElements.Add(measureElement);

     return olapReport;
}

{% endhighlight %}

![Number formatting in ASP NET pivot grid OLAP server mode](Number-Format_images/OlapServer.png)