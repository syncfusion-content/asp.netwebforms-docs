---
layout: post
title: Splitter | PivotClient | ASP.NET | Syncfusion
description: splitter
platform: aspnet
control: PivotClient
documentation: ug
---

# Splitter

I> This feature is not applicable for OLAP datasource  bound from server-side. 

You can resize Cube Dimension Browser and Axis Element Builder by setting EnableSplitter property to true.This property is disabled by default.

{% highlight html %}

    <ej:PivotClient ID="PivotClient1" runat="server" EnableSplitter="true">
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

![](Splitter_images/Splitter1.png)

![](Splitter_images/Splitter2.png)

![](Splitter_images/Splitter3.png)

![](Splitter_images/Splitter4.png)

