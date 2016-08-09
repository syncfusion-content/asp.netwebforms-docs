---
layout: post
title: Labels | PivotGauge | ASP.NET | Syncfusion
description: label
platform: aspnet
control: PivotGauge
documentation: ug
---

# Labels

## Adding Label Collection

`LabelCollection` can be directly added to the scales option within the PivotGauge control.

{% highlight html %}
    
    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <LabelCollection>
                    <ej:CircularLabels Angle="20"></ej:CircularLabels>
                </LabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

## Appearance Customization

The appearance of the Label can be customized through the following properties.

* **Angle** – used to display labels in a rotated manner.  By default, the value is 0.
* **Color** – displays the label in specified color
* **Opacity** – sets the opacity of the label. By default, the value is 1.
* **Type** – indicates the label for major intervals or minor intervals.  By default, it takes major intervals.
* **IncludeFirstValue** – includes the initial value based on user requirement.  By default, the value is “true”.
* **Font** – sets the font size, font style and font family of the label.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <LabelCollection>
                    //for Major labels
                    <ej:CircularLabels Type="Major" Color="#1AFF01" Opacity="80" IncludeFirstValue="false">
                        <Font FontFamily="Arial" FontStyle="Bold" Size="15px"></Font>
                    </ej:CircularLabels>
                    //for Minor labels
                    <ej:CircularLabels Type="Minor" Color="#FF103F" Opacity="80" IncludeFirstValue="true">
                        <Font FontFamily="Arial" FontStyle="Normal" Size="10px"></Font>
                    </ej:CircularLabels>
                </LabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Labels_images/AppearanceCustomization.png) 

## Unit Text

The `UnitText` property is used to add some text along with the labels. Normally, we indicate the unit/measurement of the numeric value through unit text. Using the `UnitTextPosition` property, the text can be positioned either in front or back.

N> By default, text appears at the back.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <LabelCollection>
                    //for Major labels
                    <ej:CircularLabels Type="Major" UnitText="$" UnitTextPosition="Front"></ej:CircularLabels>
                    //for Minor labels
                    <ej:CircularLabels Type="Minor" UnitText="$" UnitTextPosition="Front"></ej:CircularLabels>
                </LabelCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Labels_images/UnitText.png) 
