---
layout: post
title: Responsive Layout | PivotClient | ASP.NET | Syncfusion
description: This document illustrates that how to enable responsive layout rendering in ASP.NET PivotClient control
platform: aspnet
control: PivotClient
documentation: ug
---

# Responsive layout

The pivot client control supports responsive rendering based on the target device (desktop and tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in the pivot client by setting the `IsResponsive` property to true.

{% highlight html %}

    <ej:PivotClient ID="PivotClient1" runat="server" IsResponsive="true">
            <DataSource>
                <Rows>
                    <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
                </Rows>
                <Columns>
                    <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
                </Columns>
                <Values>
                    <ej:Field FieldName="Amount" FieldCaption="Amount" Format="currency"></ej:Field>
                </Values>
            </DataSource>
            <ClientSideEvents Load="onLoad" />
    </ej:PivotClient>

{% endhighlight %}

![Responsive layout in ASP NET pivot client control](Responsive-Layout_images/responsive.png)
