---
layout: post
title: Number format  | PivotGrid | ASP.NET | Syncfusion
description: number format 
platform: aspnet
control: PivotGrid
documentation: ug
---

# Number format 

Allows us to specify the required number format that PivotGrid should use in its values by setting the `format` option. Following number formats are supported:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction

## Relational

### Client Mode

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

![](Number-Format_images/RelationalClient.png)

### Server Mode

 You can set Number Format through the property `Format`. You should specify the format to the property as per the MS standard notation.
 
private PivotReport BindDefaultData()
    {
        
        PivotReport pivotSetting = new PivotReport();
        pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
        pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
        //specify the format here
        pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "E", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
        return pivotSetting;
    }

![](Number-Format_images/RelationalServer.png)

## OLAP

### Client Mode

{% highlight js %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
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

![](Number-Format_images/OlapClient.png)

### Server Mode

 Olap server mode supports the following number formats in addition to the above mentioned formats. 
* General
* RoundTrip
* FixedPoint
* HexaDecimal

N> You can set the number format through the property `Format`

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

![](Number-Format_images/OlapServer.png)