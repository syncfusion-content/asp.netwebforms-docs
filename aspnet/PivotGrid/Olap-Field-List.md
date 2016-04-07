---
layout: post
title: PivotTable Field List | PivotGrid | ASP.NET | Syncfusion
description: pivotTable field list
platform: aspnet
control: PivotGrid
documentation: ug
---

# PivotTable Field List

## Initialization  

Field List, also known as Pivot Schema Designer, allows user to add, rearrange, filter and remove fields to show data in PivotGrid exactly the way they want.

Based on the datasource, OLAP, bound to the PivotGrid control, PivotTable Field List will be automatically populated with Cube Information or Field Names. PivotTable Field List provides an Excel like appearance and behavior.

In-order to initialize PivotTable Field List, first you need to define a “div” tag with an appropriate “id” attribute which acts as a container for the widget. Then you need to initialize the PivotTable Field List by using the **"PivotSchemaDesigner"** method.

##Client Mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGroupingBar="true">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
        <Rows>
            <ej:Field FieldName="[Customer].[Customer Geography]"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="[Date].[Fiscal]"></ej:Field>
        </Columns>
        <Values>
            <ej:Field Axis="Column">
                <Measures>
                    <ej:MeasuresItems FieldName="[Measures].[Internet Sales Amount]" />
                </Measures>
            </ej:Field>
        </Values>
    </DataSource>
    <ClientSideEvents RenderSuccess="loadSchemaDesigner" />
</ej:PivotGrid>
<ej:PivotSchemaDesigner ID="PivotSchemaDesigner1" runat="server">
    <OlapSettings ShowKPI="true" ShowNamedSets="true" />
</ej:PivotSchemaDesigner>
    

<script type="text/javascript">
    function loadSchemaDesigner(args) {
        var PivotSchemaDesigner = $(".e-pivotschemadesigner").data('ejPivotSchemaDesigner');

        if (PivotSchemaDesigner.model.pivotControl == null) {
            PivotSchemaDesigner.model.pivotControl = this;
            PivotSchemaDesigner.model.layout = "excel";
            PivotSchemaDesigner.model.enableWrapper = true;
            PivotSchemaDesigner._load();
        }
        args.model.renderComplete = null;
    }
</script>
    
{% endhighlight %}

![](PivotTable-Field-List_images/OlapClientMode.png)

##Server Mode 

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="../PivotGridService">
    <ClientSideEvents  AfterServiceInvoke="OnAfterServiceInvoke"/>
</ej:PivotGrid>

<ej:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server></ej:PivotSchemaDesigner>
 
<script type="text/javascript">
 OnAfterServiceInvoke = function (evt) {
 if (evt.action == "initialize") {
  var PivotSchemaDesigner = $( ".e-pivotschemadesigner").data('ejPivotSchemaDesigner');
     if (PivotSchemaDesigner.model.pivotControl == null) {
         PivotSchemaDesigner.model.pivotControl = this;
         PivotSchemaDesigner.model.enableWrapper = true;
         PivotSchemaDesigner.model.layout = "excel";
         PivotSchemaDesigner._load();
      }
    }
  }
</script>

{% endhighlight %}

![](PivotTable-Field-List_images/pivotschema.png)


## Layout 

The top portion of the layout shows Field or Cube items in a categorized way. They can be dynamically added into the report either by drag and drop option or through simple check box selection.
 
On item(s) selection they will be placed in Row section by default except numeric based item(s) or measures, which will alone be placed in the Value section by default.

The bottom portion of the layout is segregated as below.

* Report Filter: Exclusively designed to filter an item(s) placed in this particular position of the layout. 
* Value Section: The value label usually displays the numeric value item(s) present in the report.
* Column Section: It is used to display item(s) as column header and values in the PivotGrid control. 
* Row Section: It is used to display item(s) as row header and values in the PivotGrid control.

## UI Interactions 
You can alter the report on fly through drag-and-drop operation. You can drag any item from Field List and drop into column, row, value or filter section available at the bottom of the Field List.

![](PivotTable-Field-List_images/schema.png) 

You can also alter the report on fly through check and uncheck option as an alternate. By default, fields will be added to the Row Label when checked.

![](PivotTable-Field-List_images/check-uncheck.png) 

## Filtering
Values can be filtered by checking/unchecking the check box besides them, inside the filter pop-up window. At least one value needed to be checked state while filtering otherwise “Ok” button will be disabled.

![](PivotTable-Field-List_images/filter.png) 

![](PivotTable-Field-List_images/filter1.png)

 