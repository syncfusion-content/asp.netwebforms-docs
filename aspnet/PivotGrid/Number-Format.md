---
layout: post
title: Number format  | PivotGrid | ASP.NET | Syncfusion
description: number format 
platform: aspnet
control: PivotGrid
documentation: ug
---

# Number format 

I> This feature is applicable only for Relational datasource only at Client Mode.

The PivotGrid widget values could be formatted to number, decimal, currency, percentage, date and time etc… by setting an appropriate `Format` option.

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
            args.model.dataSource.data = pivot_dataset;
        }
</script>

{% endhighlight %}

![](Number-Format_images/Numberformat.png)

