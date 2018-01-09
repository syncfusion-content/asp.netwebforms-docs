---
layout: post
title: Bullet Graph Caption | Barcode | ASP.NET Webforms | Syncfusion
description: bullet graph caption
platform: aspnet
control: BulletGraph	
documentation: ug
---

# Bullet Graph Caption

Bullet Graph supports title and subtitle to convey what is represented in Bullet Graph. They are customized using CaptionSettings property.

## Title

Title is set to Bullet Graph using text property in CaptionSettings. Caption settings also include properties like Location, Font, and TextAngle for customizing the caption of Bullet Graph.

### Location

Using `location` option, you can set the `X` and `Y` position of caption text.

### Font

Using `font` property, you can customize `font color`, `font family`, `font style`, `font weight`, `opacity`, `size` options.

{% highlight html %}



<ej:BulletGraph ID="BulletGraph1" Width="600px" Height="700px" runat="server">

            <QuantitativeScaleSettings Minimum="0" Maximum="5" Interval="1">

                <Location x="110" Y="200"/>

            </QuantitativeScaleSettings>

            <CaptionSettings Text="Revenue YTD">

                <Location Y="220" />

                <Font FontStyle="bold" FontColor="gray" Size="14px"></Font>

            </CaptionSettings>

        </ej:BulletGraph>

{% endhighlight %}

The following screenshot displays a Bullet Graph with customized caption using the above code

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img1.png)



## Subtitle

Subtitle is added to Bullet Graph using Text property of SubTitle in CaptionSettings. SubTitle also provides properties like Location, TextAngle and Font to customize subtitle similar to caption.


### Location

Using `location` option, you can set the `X` and `Y` position of caption text.

### Font

Using `font` property, you can customize `font color`, `font family`, `font style`, `font weight`, `opacity`, `size` options.


{% highlight html %}



        <ej:BulletGraph ID="BulletGraph1" Width="600px" Height="700px" runat="server">            

            <CaptionSettings Text="Revenue YTD">



                <SubTitle Text="Subtitle">

                    <Location X="20" Y="225" />

                    <Font FontStyle="italic" Size="16px"></Font>

                </SubTitle>



                <Location Y="210" />

                <Font FontStyle="bold" FontColor="gray" Size="14px"></Font>

            </CaptionSettings>

            <QuantitativeScaleSettings Minimum="0" Maximum="5" Interval="1">

                <Location x="110" Y="200"/>

            </QuantitativeScaleSettings>

        </ej:BulletGraph>


{% endhighlight %}
The following screenshot displays Bullet Graph with a SubTitle

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img2.png) 



## Indicator

You can add Indicator to bullet graph by enabling Visible and setting Text properties of Indicator in CaptionSettings. Indicator is used to represent whether target is achieved or not with text and symbol by comparing current and target values in bullet graph. 

Indicator displays a symbol along with text which is different from caption and subtitle. Images like logos can be used in indicator instead of symbols. Indicator has properties such as Symbol, Text, TextSpacing, TextAngle, Location and Font. 
{% highlight html %}


      <ej:BulletGraph ID="BulletGraph1" Width="600px" Height="700px" runat="server">            

            <CaptionSettings Text="Revenue YTD">



                <Indicator Visible="true" Text="+ $0.5 K">

                    <Location X="15" Y="240" />

                    <Symbol Shape="Triangle" Color="green">

                        <Border width="1" Color="green" />

                    </Symbol>



                </Indicator>



                <SubTitle Text="Subtitle">

                    <Location X="20" Y="225" />

                    <Font FontStyle="italic" Size="16px"></Font>

                </SubTitle>

                <Location Y="210" />

                <Font FontStyle="bold" FontColor="gray" Size="14px"></Font>

            </CaptionSettings>

            <QuantitativeScaleSettings Minimum="0" Maximum="5" Interval="1">

                <Location x="110" Y="200"/>

                <LabelSettings LabelPrefix="$" LabelSuffix="K"></LabelSettings>

            </QuantitativeScaleSettings>

        </ej:BulletGraph>


{% endhighlight  %}
The following screenshot displays a bullet graph with indicator.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img3.png)



## Trim

The title, subtitle and indicator text can be overlapped to the scale group. You can avoid the overlapped text by using the EnableTrim property of the CaptionSettings. The default value of the EnableTrim is true. 
{% highlight html %}



<ej:BulletGraph Value="8" ComparativeMeasureValue="8" Width="650" Height="150" runat="server">

      <CaptionSettings Text="Bullet Graph Title" EnableTrim=true />

</ej:BulletGraph>


{% endhighlight %}


The following screenshot displays the BulletGraph with Trim.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img4.png)



## Text Placement

All the caption group elements (caption, subtitle, and indicator) in the Bullet Graph support text positioning by using the property TextPosition available in all caption group elements. The properties, TextAlignment and TextAnchor are used to customize text placement further.

### Text Position

The property, TextPosition, is used to position the text at the top, bottom, left, and right side of the quantitative scale. The default value of this property is float. By default, text can be placed at any desired location by using the Location property. 
{% highlight html %}



<ej:BulletGraph Value="8" ComparativeMeasureValue="8" Width="650" Height="150" runat="server">

        <QuantitativeScaleSettings>

            <Location X="120" Y="40" />

        </QuantitativeScaleSettings>

        <CaptionSettings Text="Bullet Graph Title" TextPosition="Top">

            <Font FontWeight="bold" Size="20px" ></Font>

        </CaptionSettings>

    </ej:BulletGraph>

{% endhighlight  %}

The following screenshot displays the Bullet Graph with the title positioned above.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img5.png)



### Text Alignment

Alignment of text at different positions with respect to scale can be customized by using the TextAlignment property. Text can be aligned in the Near, Center, and Far locations of the scale. Text alignment depends upon TextPosition property and is not applicable when the value of the TextPosition property is Float. The default value of the TextAlignment property is Near. 
{% highlight html %}



    <ej:BulletGraph Value="8" ComparativeMeasureValue="8" Width="650" Height="150" runat="server">

        <QuantitativeScaleSettings>

            <Location X="120" Y="40" />

        </QuantitativeScaleSettings>

        <CaptionSettings Text="Revenue" TextPosition="Left" TextAnchor="Middle">

            <Font FontWeight="bold" Size="16px" ></Font>

            <SubTitle Text="$ in thousands" TextPosition="Left" TextAlignment="Center">

                <Font FontWeight="bold" Size="12px" ></Font>

            </SubTitle>

        </CaptionSettings>

    </ej:BulletGraph>


{% endhighlight %}
The following screenshot displays the Bullet Graph with the title and subtitle at different alignments.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img6.png)



### Text Anchor

Text elements aligned at the same position are anchored by using the TextAnchor property. These can be anchored at the Start, Middle, and End. The default value of this property is Start and applicable only when two or more text elements are aligned at the same position. 
{% highlight html %}



    <ej:BulletGraph Value="8" ComparativeMeasureValue="8" Width="650" Height="150" runat="server">

        <QuantitativeScaleSettings>

            <Location X="120" Y="40" />

        </QuantitativeScaleSettings>

        <CaptionSettings Text="Revenue" TextPosition="Left" TextAnchor="Middle">

            <Font FontWeight="bold" Size="16px" ></Font>

            <SubTitle Text="$ in thousands" TextPosition="Left" TextAlignment="Center">

                <Font FontWeight="bold" Size="12px" ></Font>

            </SubTitle>

        </CaptionSettings>

    </ej:BulletGraph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img7.png)



### Padding

The space required between text and quantitative scale is customized by using the Padding property. The default value of this property is 5 and not applicable when the value of the TextPosition property is Float. 
{% highlight html %}



<ej:BulletGraph Value="8" ComparativeMeasureValue="5" Width="650" Height="150" runat="server">

        <QuantitativeScaleSettings>

            <Location X="120" Y="40" />

        </QuantitativeScaleSettings>

        <CaptionSettings Text="Profit in %" TextPosition="Left" TextAlignment="Center" Padding="10">

            <Font FontWeight="bold" Size="16px" ></Font>            

        </CaptionSettings>

    </ej:BulletGraph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img8.png)



