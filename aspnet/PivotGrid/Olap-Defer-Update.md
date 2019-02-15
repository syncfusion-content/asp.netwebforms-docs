---
layout: post
title: Defer Update | PivotGrid | ASP.NET | Syncfusion
description: defer update
platform: aspnet
control: PivotGrid
documentation: ug
---

# Defer update

I> This feature is applicable for the OLAP data source only at server mode.

The defer update support allows you to refresh the control only on-demand and not during every UI interaction.

{% highlight html %}

<cc1:PivotGrid ID="PivotGrid1" runat=server url="/PivotGridService" ClientIDMode="Static">
    <ClientSideEvents AfterServiceInvoke="OnAfterServiceInvoke" /> </cc1:PivotGrid>

<cc1:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server></cc1:PivotSchemaDesigner>

<script type="text/javascript">
    OnAfterServiceInvoke = function(evt) {
        if (evt.action == "initialize") {
            var PivotSchemaDesigner = $("#PivotSchemaDesigner").data('ejPivotSchemaDesigner');
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

![Defer update in ASP NET pivot grid OLAP server mode](Defer-Update_images/Defer-Update_images1.png)

