---
layout: post
title: Defer-Update
description: defer update
platform: aspnet
control: OLAP Client
documentation: ug
---

# Defer Update

Defer Update support will allow user to refresh the control only on-demand and not during every UI interaction.  To enable this functionality set the `enableDeferUpdate` property to "true".

The following code example explains on how to enable Defer Update in the OlapClient control.

{% highlight html %}

   <ej:OlapClient ID="OlapClient1" runat="server" Url="../wcf/OlapClientService.svc" Title="OLAP Browser" EnableDeferUpdate="true" ClientIDMode="Static"> </ej:OlapClient>

{% endhighlight %}

![](Defer-Update_images/Defer-Update_images1.png) 

_Before Defer Update_

![](Defer-Update_images/Defer-Update_images2.png) 

_After Defer Update_