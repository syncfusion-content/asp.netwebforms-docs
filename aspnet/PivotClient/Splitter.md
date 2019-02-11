---
layout: post
title: Splitter | PivotClient | ASP.NET | Syncfusion
description: splitter
platform: aspnet
control: PivotClient
documentation: ug
---

# Splitter

You can resize the cube dimension browser and axis element builder by setting the `EnableSplitter` property to true. This property is disabled by default.

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

![Left move of splitter in ASP NET pivot client control](Splitter_images/Splitter1.png)

![Resizing axis element builder in ASP NET pivot client control](Splitter_images/Splitter2.png)

![Right move of splitter in ASP NET pivot client control](Splitter_images/Splitter3.png)

![Resizing cube dimension browser in ASP NET pivot client control](Splitter_images/Splitter4.png)

