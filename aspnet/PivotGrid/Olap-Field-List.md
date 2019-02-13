---
layout: post
title: PivotTable Field List | PivotGrid | ASP.NET | Syncfusion
description: pivotTable field list
platform: aspnet
control: PivotGrid
documentation: ug
---

# Pivot table field list

## Initialization

Field list, also known as Pivot Schema Designer, allows you to add, rearrange, filter, and remove the fields to show the data in pivot grid exactly the way as you desired.

Based on the data source and OLAP bound to the pivot grid control, the pivot table field list will be automatically populated with the cube information or field names. The pivot table field list provides an Excel like appearance and behavior.

To initialize the pivot table field list, first you can define a “div” tag with an appropriate “id” attribute which acts as a container for the control. Then, you can initialize the pivot table field list by using the **"PivotSchemaDesigner"** method.

### Client mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server" EnableGroupingBar="true">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="https://bi.syncfusion.com/olap/msmdpump.dll">
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

![Field list in ASP NET pivot grid OLAP client mode](PivotTable-Field-List_images/OlapClientMode.png)

### Server mode

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="/PivotGridService.svc">
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

![Excel structure of field list in ASP NET pivot grid control](PivotTable-Field-List_images/pivotschema.png)


## Layout

The top portion of the layout shows the field or cube items in a categorized way. The field or cube items can be dynamically added to the report either by drag and drop option or through the simple check box selection.

On item(s) selection, they will be placed in the row section by default except numeric based item(s) or measures, which will alone be placed in the value section by default.

The bottom portion of the layout is segregated as below:

* Report filter: Exclusively designed to filter the item(s) placed in the particular position of the layout.
* Value section: The value label usually displays the numeric value item(s) present in the report.
* Column section: Displays the item(s) as column header and values in the pivot grid control.
* Row section: Displays the item(s) as row header and values in the pivot grid control.

## UI interactions

### By drag and drop

You can alter the report on fly through the drag-and-drop operation. You can drag any item from the field list and drop into the column, row, value, or filter section available at the bottom of the field list.

![Drag and drop in ASP NET field list](PivotTable-Field-List_images/schema.png)

### By tree view selection

You can alter the report on fly through the check and uncheck option as an alternate. By default, the fields will be added to the row label when checked.

![Filtering in ASP NET field list](PivotTable-Field-List_images/check-uncheck.png)

### By context menu

You can also alter the report by using the context menu.

![Context menu in pivot button of ASP NET field list](PivotTable-Field-List_images/Olap_Pivotbutton_Context.png)

![Context menu in tree view elements of ASP NET field list](PivotTable-Field-List_images/Olap_Treeview_Context.png)

## Searching values

The search option available in the field list allows you to search a specific value that should be filtered from the list of values in the filter pop-up window.

![Tree drop icon in ASP NET field list](PivotTable-Field-List_images/filter.png)

![Searching in member editor dialog of ASP NET field list](PivotTable-Field-List_images/search.png)

## Filtering
Values can be filtered by checking/unchecking the check box besides them in the filter pop-up window. At least, one value should in the checked state while filtering. If else, the OK button will be disabled.

![Tree drop icon click in ASP NET field list](PivotTable-Field-List_images/filter.png)

![Filtering in member editor dialog of ASP NET field list](PivotTable-Field-List_images/filter1.png)
