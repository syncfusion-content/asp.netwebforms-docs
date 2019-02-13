---
layout: post
title: Calculated Members | PivotClient | ASP.NET | Syncfusion
description: Calculated Members
platform: aspnet
control: PivotClient
documentation: ug
---

# Calculated Members

I> This feature is applicable only for Server Mode bound with OLAP data source.

Calculated members are the customized dimension members or measures that are defined based on the cube data. Values for calculated members are computed at run-time.

The two types of calculated members are as follows:

Calculated Measure – Calculated measure created from a measure element.

Calculated Dimension – Calculated member created from a dimension element.

PivotClient provides support to insert new calculated members based on the existing OLAP field members either through UI dialog or code behind.

## Through UI

To show the icon in toolbar panel, we need to set the property `EnableCalculatedMember` as `true` under `ToolbarIconSettings` object.

{% highlight html %}

    <ej:PivotClient ID="PivotClient1" runat="server"  Url="../api/OlapClient" Title="OLAP Browser" ClientIDMode="Static">
        //..
        <ToolbarIconSettings  EnableCalculatedMember="true" />
    </ej:PivotClient>

{% endhighlight %}

![Calculated members icon in ASP NET pivot client control](Calculated-Members_images/icon.png)

To insert a new calculated member, open the Calculated Member dialog by clicking the icon available in toolbar panel. We can define following options inside the dialog.

    Caption - To set the name for the calculated member.
    Expression - To set the formula for the calculated member where you can insert required members through Cube Dimension Browser by a simple drag and drop option with required operators to make formula.
    Member Type - To specify the hierarchy of the member set in expression.
    Format String - To set the format for the calculated member.

![Calculated members dialog in ASP NET pivot client control](Calculated-Members_images/dialog.png)

## Through Code Behind

For code-behind, we can create the calculated members by defining formula in OlapReport with the following definitions.

    Name – Name of the calculated member.
    Expression – Expression to form the calculated member.
    Measure/Dimension Element – You should add a measure or dimension element from which the calculated member should be created.

Following steps will explain how to create and add a calculated member in an OlapReport:

    1. Create the dimension measure or element from which the calculated member has to be created.
    2. Create the calculated member by giving the name and expression.
    3. Add the element created in Step 1 to the calculated member.
    4. Once the calculated member is defined, add that member to the calculated members collection in the OlapReport.
    5. Add the newly created calculated members in categorical or series axis of an OlapReport.

Following code snippet will describe the creation and addition of a calculated members in OlapReport:

### Calculated Measure

{% highlight c# %}

    MeasureElement measureElement = new MeasureElement();

    measureElement.Name = "Order Quantity";

    CalculatedMember calculatedMeasure = new CalculatedMember();

    calculatedMeasure.Name = "Oder on Discount";

    calculatedMeasure.Expression = "[Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)";

    calculatedMeasure.AddElement(measureElement);

    olapReport.CalculatedMembers.Add(calculatedMeasure);

    olapReport.CategoricalElements.Add(calculatedMeasure);

{% endhighlight %}

### Calculated Dimension

{% highlight c# %}

     DimensionElement internalDimension = new DimensionElement();

    internalDimension.Name = "Product";

    internalDimension.AddLevel("Product Categories", "Category");

    // Calculated Dimension

    CalculatedMember calculatedDimension = new CalculatedMember();

    calculatedDimension.Name = "Bikes & Components";

    calculatedDimension.Expression = "([Product].[Product Categories].[Category].[Bikes] + [Product].[Product Categories].[Category].[Components] )";

    calculatedDimension.AddElement(internalDimension);

    olapReport.CalculatedMembers.Add(calculatedDimension);

    olapReport.CategoricalElements.Add(calculatedDimension);

{% endhighlight %}

![Calculated members in ASP NET pivot client control](Calculated-Members_images/members.png)