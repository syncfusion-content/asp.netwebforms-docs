---
layout: post
title: Named Set | PivotTreeMap | ASP.NET | Syncfusion
description: named set
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# Named sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members, that can be created by combining the cube data, arithmetic operators, numbers, and functions.

## Client mode

You can bind the named sets in the pivot tree map by setting it's unique name in the `FieldName` property in the row or column axis and `isNamedSets` Boolean property to true.

{% highlight js %}

<!--Create a tag which acts as a container for PivotTreeMap--> 
<form id="form1" runat="server">
    <ej:PivotTreeMap ID="PivotTreeMap1" runat="server" IsResponsive="true" ClientIDMode="Static">
        <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
                <Columns>
                    <ej:Field FieldName="[Customer].[Customer Geography]"></ej:Field>
                </Columns>
                <Rows>
                    <ej:Field FieldName="[Core Product Group]" isNamedSets="true"></ej:Field>
                </Rows>
                <Values>
                    <ej:Field Axis="Column">
                        <Measures>
                            <ej:MeasuresItems FieldName="[Measures].[Internet Sales Amount]" />
                        </Measures>
                    </ej:Field>
                </Values>
            </DataSource>
    </ej:PivotTreeMap>
    <asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
</form>

<! --Tooltip labels can be localized here-->
<script id="tooltipTemplate" type="application/jsrender">
    <div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
        <div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
    </div>
</script>  

{% endhighlight %}

![](NamedSets_images/namedset.png)


## Server mode

You can add the named sets to the pivot tree map by using the `NamedSetElement` class in the OlapReport.

{% highlight C# %}

OlapReport olapReport = new OlapReport(); 
olapReport.Name = "Customer Report"; 
olapReport.CurrentCubeName = "Adventure Works"; 

DimensionElement dimensionElementColumn = new DimensionElement(); 
dimensionElementColumn.Name = "Customer"; 
dimensionElementColumn.AddLevel("Customer Geography", "Country ");
 
MeasureElements measureElementColumn = new MeasureElements(); 
measureElementColumn.Elements.Add(new MeasureElement { 
Name = "Internet Sales Amount" 
}); 

NamedSetElement dimensionElementRow = new NamedSetElement(); 
dimensionElementRow.Name = "Core Product Group"; 

olapReport.CategoricalElements.Add(dimensionElementColumn); 
olapReport.CategoricalElements.Add(measureElementColumn); 
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight %}

![](NamedSets_images/servernamedset.png)


