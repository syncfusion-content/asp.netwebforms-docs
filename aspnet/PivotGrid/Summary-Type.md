---
layout: post
title: Summary Type | PivotGrid | ASP.NET | Syncfusion
description: summary type
platform: aspnet
control: PivotGrid
documentation: ug
---

# Summary Type

I> This feature is applicable only for Relational datasource only at Client Mode.

Allow us to specify the required summary type that PivotGrid should use in its summary cells. “Sum” is the default summary type. Following summary types that are supported:

* Sum
* Average
* Count
* Min
* Max

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
        </Rows>
       <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
       </Columns>
       <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount" SummaryType="Average"></ej:Field>
            <ej:Field FieldName="Quantity" FieldCaption="Quantity" SummaryType="Sum"></ej:Field>
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

![](Getting-Started_images/purejssummarytype.png)

