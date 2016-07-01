---
layout: post
title: Pointers | PivotGauge | ASP.NET | Syncfusion
description: pointers
platform: aspnet
control: PivotGauge
documentation: ug
---

# Pointers

## Pointer Types

PivotGauge pointers has two types such as,

* Needle
* Marker

Needle type pointers are the default pointers which is always located at the center of the Gauge. There are 5 different shapes for the needle pointers which are Rectangle, Triangle, Trapezoid, Arrow and Image.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    <ej:Pointers Type="Needle" NeedleType="Trapezoid"></ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/NeedlePointer.png) 

For marker pointer, the available shapes are Rectangle, Triangle, Ellipse, Diamond, Pentagon, Circle, Slider, Pointer, Wedge, Trapezoid, RoundedRectangle and Image.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    <ej:Pointers Type="Marker" MarkerType="Diamond"></ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/MarkerPointer.png) 

## Adding Pointer Collection

Pointer collection can be directly added to the scales option within the PivotGauge control as an array. 

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    <ej:Pointers Type="Needle" NeedleType="Triangle"></ej:Pointers>
                    <ej:Pointers Type="Marker" MarkerType="Diamond"></ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight  %}

![](Pointers/AddingPointerCollection.png)

## Appearance Customization

The appearance of the pointer can be customized through the following properties.

* **Border** – sets the “Color” and “Width” of the pointer border.
* **BackgroundColor** – sets the background color of the pointer.
* **Length** – sets the length of the pointer.
* **Width** – sets the width of the pointer.
* **Opacity** – sets the opacity of the pointer.  By default, the value is 1.
* **Type** – sets the type of the pointer.  By default, the type is “Needle”.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    //For customizing needle pointer
                    <ej:Pointers Type="Needle" NeedleType="Triangle" BackgroundColor="yellow" Length="120" Width="7" Opacity="60">
                        <Border Color="green" Width="2" />
                    </ej:Pointers>
                    //For customizing marker pointer
                    <ej:Pointers Type="Marker" MarkerType="Diamond" BackgroundColor="yellow" Length="25" Width="15" Opacity="80">
                        <Border Color="green" Width="2" />
                    </ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/AppearanceCustomization.png) 

## Pointer Position

Pointer can be positioned with the help of below two properties.

* **DistanceFromScale** -  defines the distance between scale and pointer. By default, the value is 0.
* **Placement** -  defines the location of the pointer. By default, the value is “Center”.

N> Both the properties can be applied only if the pointer type is set to “Marker”. Needle pointer type appears only at the center of the control, which is its default position.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    <ej:Pointers Type="Marker" Placement="Far" DistanceFromScale="2">
                    </ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/PointerPosition.png)

## Pointer Image

It is possible to replace the pointers with image. To view the pointers as image, we need to set the appropriate location in the `ImageUrl` property.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    //For replacing needle pointer with image
                    <ej:Pointers Type="Needle" NeedleType="Image" ImageUrl="../image.png"></ej:Pointers>
                    //For replacing marker pointer with image
                    <ej:Pointers Type="Marker" MarkerType="Image" ImageUrl="../image.png"></ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/PointerImage.png)

## Pointer Value Text

To display the current value of the pointers in PivotGauge control, **"PointerValueText"** option inside pointers is used.  Following are the properties used to enable and customize the pointer value text.
 
* **ShowValue** – enables the pointer value text by setting the property to “true”. By default, its value is “true”.
* **Distance** – sets the distance between pointer and text.
* **Color** – sets the color of the text.
* **Opacity** – sets the opacity of the text. By default, its value is 1.
* **Angle** – sets the rotation angle of the text. By default, its value is 0.
* **Font** – sets the font size, font style and font family of the text.

{% highlight html %}

    <ej:PivotGauge ID="PivotGauge1" runat="server">
        <Scales>
            <ej:CircularScales>
                <PointerCollection>
                    //For needle type
                    <ej:Pointers Type="Needle">
                        <PointerValueText ShowValue="true" Distance="10" Color="red" Opacity="70" Angle="20">
                            <Font FontFamily="Arial" FontStyle="Normal" Size="15px"></Font>
                        </PointerValueText>
                    </ej:Pointers>
                    //For marker type
                    <ej:Pointers Type="Marker">
                        <PointerValueText ShowValue="true" Distance="40" Color="red" Opacity="70" Angle="-40">
                            <Font FontFamily="Arial" FontStyle="Normal" Size="15px"></Font>
                        </PointerValueText>
                    </ej:Pointers>
                </PointerCollection>
            </ej:CircularScales>
        </Scales>
    </ej:PivotGauge>

{% endhighlight %}

![](Pointers/PointerValueText.png)