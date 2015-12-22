---
layout: post
title: Defer-Update | PivotGrid | ASP.NET | Syncfusion
description: defer update
platform: aspnet
control: PivotGrid
documentation: ug
---

# Defer Update

Defer Update support allows you to refresh the control only on-demand and not during every UI interaction.

{% highlight html %}

<cc1:PivotGrid ID="PivotGrid1" runat=server url="../wcf/OLAPService.svc" ClientIDMode="Static" EnableDeferUpdate="true">
    <ClientSideEvents AfterServiceInvoke="OnAfterServiceInvoke" /> </cc1:PivotGrid>
   
<cc1:PivotSchemaDesigner ID="PivotSchemaDesigner" runat=server></cc1:PivotSchemaDesigner>

{% endhighlight %}

![](Defer-Update_images/Defer-Update_images1.png)

