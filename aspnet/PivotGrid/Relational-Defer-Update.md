---
layout: post
title: Defer-Update | PivotGrid | ASP.NET | Syncfusion
description: This document illustrates that how to enable defer-update in server mode of ASP.NET PivotGrid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Defer update

I> This feature is applicable for the relational data source at server mode only.

The defer update support allows you to refresh the control only on-demand and not during every UI interaction.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat=server url="/RelationalService.svc" ClientIDMode="Static" >
    <ClientSideEvents AfterServiceInvoke="OnAfterServiceInvoke" /> </ej:PivotGrid>

<ej:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server></ej:PivotSchemaDesigner>

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

![Defer update support in ASP NET pivot grid control](Defer-Update_images/RelationalDeferUpdate.png)

