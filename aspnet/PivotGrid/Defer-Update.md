---
layout: post
title: Defer-Update
description: defer update
platform: aspnet
control: PivotGrid
documentation: ug
---

# Defer Update

Defer Update support will allow user to refresh the control only on-demand and not during every UI interaction. To enable this functionality, we need to set `enableDeferUpdate` property to "true".

The following code example explains on how to enable Defer Update in the PivotGrid control.

{% highlight html %}

<cc1:PivotGrid ID="PivotGrid1" runat=server url="../wcf/OLAPService.svc" ClientIDMode="Static" EnableDeferUpdate="true">
    <ClientSideEvents AfterServiceInvoke="OnAfterServiceInvoke" /> </cc1:PivotGrid>
   
<cc1:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server></cc1:PivotSchemaDesigner>

{% endhighlight %}

{% highlight js %}

OnAfterServiceInvoke = function(evt)
{
    if (evt.action == "initialize")
    {
        var PivotSchemaDesigner = $(".e-pivotschemadesigner").data('ejPivotSchemaDesigner');
        if (PivotSchemaDesigner.model.pivotControl == null)
        {
            PivotSchemaDesigner.model.pivotControl = this;
            PivotSchemaDesigner.model.layout = "excel";
            PivotSchemaDesigner.model.enableWrapper = true;
            PivotSchemaDesigner._load();
        }
    }
}

{% endhighlight %}

![](Defer-Update_images/Defer-Update_images1.png)

