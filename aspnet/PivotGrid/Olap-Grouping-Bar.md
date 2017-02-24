---
layout: post
title: Grouping Bar | PivotGrid | ASP.NET | Syncfusion
description: grouping bar
platform: aspnet
control: PivotGrid
documentation: ug
---

# Grouping Bar

## Initialization

Grouping Bar allows user to dynamically alter the report by filter and remove operations in the PivotGrid control. Based on the OLAP datasource and report bound to the PivotGrid control, Grouping Bar will be automatically populated. You can enable Grouping Bar option in PivotGrid by setting the `EnableGroupingBar` property to true.

### Client Mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGroupingBar="true">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
        <Rows>
            <ej:Field FieldName="[Date].[Fiscal]"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="[Customer].[Customer Geography]"></ej:Field>
        </Columns>
        <Values>
            <ej:Field Axis="Column">
                <Measures>
                    <ej:MeasuresItems FieldName="[Measures].[Internet Sales Amount]" />
                </Measures>
            </ej:Field>
        </Values>
    </DataSource>
</ej:PivotGrid>

</ej:PivotGrid>

{% endhighlight %}

![](Grouping-Bar_images/OLAPClientGB.png)

### Server Mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="/PivotGridService" EnableGroupingBar="true">
</ej:PivotGrid>

{% endhighlight %}

![](Grouping-Bar_images/OLAPServerMode.png)

## Drag and Drop

You can alter the report on fly through drag-and-drop operation.

![](Grouping-Bar_images/GBar_Olap.png)

## Context Menu

You can also alter the report by using context menu.

![](Grouping-Bar_images/CMenu_Olap.png)

## Searching Values

Search option available in Grouping Bar allows you to search a specific value that needs to be filtered from the list of values inside the filter pop-up window.

![](Grouping-Bar_images/OlapFilterIcon.png)

![](Grouping-Bar_images/olapclientsearching.png)

## Filtering Values

Filtering option available in Grouping Bar allows you to select a specific set of values that needs to be displayed in the PivotGrid control. At least one value needed to be in checked state while filtering otherwise “Ok” button will be disabled.

![](Grouping-Bar_images/OlapFilterIcon.png)

![](Grouping-Bar_images/OlapFilterDialog.png)

## Removing Field

Remove option available in the Grouping Bar allows you to completely remove a specific field from the PivotGrid control. Remove operation can be either achieved by clicking remove icon available inside each field or by dragging and dropping field out of Grouping Bar region.

![](Grouping-Bar_images/OlapRemoveIcon.png)

![](Grouping-Bar_images/OlapRemove.png)

