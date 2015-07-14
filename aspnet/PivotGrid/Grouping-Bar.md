---
layout: post
title: Grouping-Bar
description: grouping bar
platform: aspnet
control: PivotGrid
documentation: ug
---

## Grouping Bar

> _Note: This feature is applicable only for Relational datasource._

The PivotGrid control supports Grouping bar that allows you to filter, sort, and remove members of the relational data loaded in the PivotGrid control. The grouped report can also be changed dynamically by using the drag and drop operations.

The following code example explains on how to enable Grouping bar within the PivotGrid control.

&lt;ej:PivotGrid ID="PivotGrid1" runat=server url="../wcf/RelationalService.svc"    EnableGroupingBar="true"  ClientIDMode="Static"&gt;

    &lt;ClientSideEvents   AfterServiceInvoke="OnAfterServiceInvoke"/&gt;

&lt;/ej:PivotGrid&gt;

&lt;ej:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server&gt;

&lt;/ej:PivotSchemaDesigner&gt;



OnAfterServiceInvoke = function (evt) {

    if (evt.action == "initialize") {

        var PivotSchemaDesigner = $(".e-pivotschemadesigner").data('ejPivotSchemaDesigner');

        if (PivotSchemaDesigner.model.pivotControl == null) {

            PivotSchemaDesigner.model.pivotControl = this;

            PivotSchemaDesigner.model.layout = "excel";

            PivotSchemaDesigner.model.enableWrapper = true;

            PivotSchemaDesigner._load();

        }

    }

}



{ ![](Grouping-Bar_images/Grouping-Bar_img1.png) | markdownify }
{:.image }




The following operations can be achieved by using the Grouping bar:

Filtering

Filtering option available in the Grouping bar allows you to select a specific set of values that needs to be displayed in the PivotGrid control and hides the rest. By default, the filtering option is applicable only for the Row, Column and Filter areas.

Sorting

Sorting option available in the Grouping bar allows you to sort values besides the respective PivotItem in the PivotGrid control. This option is applicable for the PivotItems available only in the Row and Column areas. The sort indicator present inside the button indicates whether the values are in ascending or descending order. Normally, the up arrow indicates ascending order and the down arrow indicates descending order. By default, the values are sorted in ascending order.

Remove

Remove option available in the Grouping bar allows you to remove a specific PivotItem from the PivotGridcontrol.

