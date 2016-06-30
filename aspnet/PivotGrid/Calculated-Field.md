---
layout: post
title: Calculated Field  | PivotGrid | ASP.NET | Syncfusion
description: calculated field
platform: aspnet
control: PivotGrid
documentation: ug
---

# Calculated Field

N> This feature is applicable only for Relational data source.

PivotGrid provides support to insert a new calculated field based on the existing Pivot Fields either through Calculated Field dialog or code behind.

### Through UI
To insert a new calculated Field, open the Calculated Field dialog using the Grouping Bar context menu. 

We can define **Name** for the new Calculated Field and **Formula** can be entered by inserting required fields through **Fields** section. For inserting numbers and operators, you can use formula pop-up as shown in the below screen-shot.

![](Calculated-Field_images/Calculated-Field-Popup.png)

Click **Add** for adding that Calculated Field and **OK** to populate the PivotGrid control.

#### Through Code-behind

Calculated Field can be created at code-behind by defining formula based on the existing Pivot Fields in the PivotGrid. To indicate a field as a calculated field we need to set **"IsCalculatedField"** property to true and **"Formula"** property to set the expression.


{% highlight html %}

  <ej:PivotGrid ID="PivotGrid1" EnableGroupingBar="true" runat="server" ClientIDMode="Static">
        <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country" SortOrder="Ascending"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
                <ej:Field FieldName="Price" FieldCaption="Price" IsCalculatedField="true" Formula="Amount * 15"></ej:Field>
            </Values>
        </DataSource>
  </ej:PivotGrid>

{% endhighlight %}

![](Calculated-Field_images/Calculated-Field1.png)
