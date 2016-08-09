---
layout: post
title: Custom labels | PivotGauge | ASP.NET | Syncfusion
description: custom labels
platform: aspnet
control: PivotGauge
documentation: ug
---

# Custom labels

## Adding Custom Label Collection

You can apply custom custom label Collection by using `CustomLabelCollection` which can be directly added to the scales option within the PivotGauge control.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <CustomLabelCollection>
                    <ej:CircularCustomLabel>
                        <Position X="180" Y="290" />
                    </ej:CircularCustomLabel>
                </CustomLabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

## Appearance Customization

The appearance of the custom labels can be changed through the following properties.

* **Position** – used to set the position of the labels.
* **Font** – sets the font size, font style and font family of the label text.
* **Color** – sets the color of the label text.
* **TextAngle** – rotates the label to a specified angle. By default, the value is 0.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <CustomLabelCollection>
                    <ej:CircularCustomLabel Color="blue" TextAngle="20">
                        <Position X="180" Y="320" />
                        <Font FontFamily="Segoe UI" FontStyle="Normal" Size="12px"></Font>
                    </ej:CircularCustomLabel>
                </CustomLabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Custom-Label_images/AppearanceCustomization.png) 

## Multiple Custom Labels

Multiple ranges can be added in `CustomLabelCollection` to the scales option within the PivotGauge control.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <CustomLabelCollection>
                    <ej:CircularCustomLabel Color="red">
                        <Position X="180" Y="150" />
                    </ej:CircularCustomLabel>
                    <ej:CircularCustomLabel Color="green">
                        <Position X="180" Y="320" />
                    </ej:CircularCustomLabel>
                    <ej:CircularCustomLabel Color="blue">
                        <Position X="180" Y="290" />
                    </ej:CircularCustomLabel>
                </CustomLabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Custom-Label_images/MultipleCustomLabels.png) 